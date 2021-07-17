### Evénements


## Introduction
CLIENTXCMS introduit un système d'évenement basé sur le PSR-14. Il permet d'effectuer une logique quand le système ou l'utilisateur fait une action.
Dans cet exemple nous allons prendre un message Flash lors d'une nouvelle connexion d'un utilisateur.


#### Créer son propre évenement
```php
<?php

namespace App\Auth;

use ClientX\Event\Event as BaseEvent;
use ClientX\Auth\User;

class LoginEvent extends BaseEvent {
    /**
    * Nom unique de l'évement s'y attacher plus tard
    * 
    */
    public $name = "auth.login";

    /*
    * Donne un utilisateur à l'évenement
    */
    public function __construct(User $user)
    {
        $this->setTarget($user);
    }

    /*
    * Revoie l'utilisateur passé plus haut
    */
    public function getTarget():User
    {
        return parent::getTarget();
    }
}
```
#### Déclencher son premier évenement
Une fois l'évenement créé, il faut le déclencher au moment voulut.
Dans une Action ou un Service

```php

<?php

namespace App\Admin\Actions\Auth;

use App\Admin\DatabaseAdminAuth;
use App\Auth\Event\BadPasswordEvent;
use App\Auth\Event\LoginEvent;
use ClientX\Actions\Action;
use ClientX\Event\EventManager;
use ClientX\Response\RedirectResponse;
use ClientX\Router;
use ClientX\Session\FlashService;
use ClientX\Session\SessionInterface;
use ClientX\Translator\Translater;
use Psr\Http\Message\ServerRequestInterface;

class LoginAttemptAction extends Action
{

    private SessionInterface $session;

    public function __construct(
        Router $router,
        SessionInterface $session,
        EventManager $event,
        DatabaseAdminAuth $auth,
        Translater $translater
    ) {
        $this->router = $router;
        $this->session = $session;
        $this->event = $event;
        $this->auth = $auth;
        $this->translater = $translater;
    }

    public function __invoke(ServerRequestInterface $request)
    {
        $params = $request->getParsedBody();
        $user = $this->auth->login($params['password'], $params['email'], false);
        if ($user && password_verify($params['password'], $user->getPassword())) {
            $this->event->trigger(new LoginEvent($user));
            $path = $this->session->get('auth.redirect') ?: $this->router->generateUri('admin');
            $this->session->delete('auth.redirect');
            return new RedirectResponse($path);
        } else {
            if ($user != null) {
                $this->event->trigger(new BadPasswordEvent($request));
            }
            (new FlashService($this->session))->error($this->trans("account.login.norecord"));
        }
        return $this->redirectToRoute('admin.login');
    }
}

```
####  Effectuer la logique du premier évenement

```php

<?php
namespace App\Auth\Event;
use App\Auth\LoginEvent;
use ClientX\Session\FlashService;


/**
* Classe qui va effectuer la logique
*/
class NewLoginEvent
{
    private FlashService $flash;
    /*
    * Création de l'instance via le container et demandant le FlashService
    */
    public function __construct(FlashService $flash)
    {
        $this->flash = $flash;
    }
    public function __invoke(LoginEvent $loginEvent)
    {
        // @var App\Auth\User
        $user = $loginEvent->getTarget();
        $this->flash->success(sprintf("Logged in successfully as %s", $user->getEmail()));
    }
}

```
### Modules

## Introduction

Un module vous permet d'ajouter de nouvelles fonctionnalités à clientx, vous pouvez en créer qui correspond à vos besoins ou regarder notre [place de marché](https://clientx.fr/market).

## Strusture

Il y a pas de struture précise à respecter pour que le module soit prit en compte. Mais vous pouvez suivre cet exemple pour bien débuter ou regarder comment les modules déjà existant sont structurer.



```
src/  <-- Dossier contenant les différents modules installés
|  Example/  <-- nom de votre module
|  |  config.php  <-- Le fichier de configuration de votre module
|  |  db/
|  |  |  migrations/ <-- Le dossier contenant les migrations de votre module
|  |  |  seeds/ <-- Le dossier contenant les seed de votre module
|  |  ExempleModule.php/ <-- La classe source du module
```

## config.php

Le fichier `config.php` est un fichier de définition, peut être renomer, placer n'importe où dans les sources. Il doit retourner un *tableau PHP* et sera injecter dans le **[injecteur de dépendance](https://php-di.org)**. 

```
<?php

use function DI\autowrire;
use function ClientX\setting;

return [
    'exemple.key' => 'ABC',
    App\Exemple\ExempleClass::class => autowrire()->constructorParameter('key','exemple.key'), // Injectera 'ABC',
    'exemple.actived' => setting('exemple_actived', false) // Récupére dans la configuration ou renvoi la valeur pas défaut
];

?>
```

## ExempleModule 

Le fichier `ExempleModule.php` est une classe, peut être renomer, il est obligatoire. Il sert à renseigner les routes, le fichier de configuration, migrations et seeding.

```
<?php
// src/Exemple/ExempleModule.php
namespace App\Exemple;

use ClientX\Module;
use ClientX\Router;
use Psr\Container\ContainerInterface;

class ExempleModule extends Module
{

    const MIGRATIONS = __DIR__ . '/db/migrations';
    const SEEDS = __DIR__ . '/db/seeds';
    const DEFINITIONS = __DIR__ . '/config.php'; 

    public function __construct(ContainerInterface $container)
    {
        /** @var Router */
        $router = $container->get(Router::class);
        $router->any("/exemple", function() { return 'exemple'}, 'exemple');
        $router->get("/exemple/{id:\d+}, App\Exemple\Action\ExempleAction::class, 'exemple');
    }
}

```

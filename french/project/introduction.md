## Documentation
![Logo](https://clientx.fr/assets/images/ClientXLight.png "ClientX")

**Prérequis**
- PDO
- PHP 7.4+
- MySQL
- Extension GD PHP
- Composer
- Extension JSON
....

**Modules préinstallés**
- Account
- Auth
- Admin
- Basket
- Contact
- Main
- PayPal
- Paysafecard
- Pterodactyl
- Shop (comprennant les services)
- Support
- Task
- Wiki

**Installer ou retirer des modules**

Il faut faire preuve de bon sens. Si vous désactiver le module de Authentification, Forcement, vous pourrez plus vous connecter à rien. Soyez logique. Mais vous pouvez Désactiver des modules. Il suffit de commenter la ligne dans le fichier ```/public/index.php``` qui devrait resembler à ça : ``->addModule(App\Wiki\WikiModule::class)``. Egalement, si il y a des middlewares qui sont rajouter par le modules il faut faire le même procéder avec la méthode ``->pipe(App\Wiki\WikiMiddleware::class)``. 

Pour ajouter, tout simplement suivez la documentation du module, c'est du cas par cas pour l'installation de module.


**Installation**

1) Mettre à jours les dépendances via Composer

   Pour Mettre à jours, il suffit de faire la commande suivante dans le dossier ou ce trouve l'espace client : 
    ```composer.phar update```
    Si la commande ne fonctionne il faut sûrement installer composer. https://getcomposer.org/docs/
    Un dossier ```vendor``` devrait se créer, pas de panique.


2) Installation de la base de données
    Configurer les accès dans le fichier ```/config/config.php```. Mettez bien des identifiants sécurisé. 
    Puis, tapez la commander ```./vendor/bin/phinx migrate``` pour executer les migrations. Vous pouvez également Remplir votre base de données avec des données prédéfinis avec la commande ```./vendor/bin/phinx seed:run```
    Pour plus d'informations sur phinx.org

3) Configuration de l'espace client et module

   Toute la configuration est disponible dans le dossier ```/config```. Chaque module à sa propre configuration. Vous pouvez changer quelques valeurs comme la licence ou le nom de l'application.

4) Racine publique

   Pour des mesures de sécurité, le code est un crant plus bas que le dossier racine, le dossier ```/public```. Il faut juste pointer votre hébergeur web sur ce bon dossier ou faire une configuration Apache ou Nginx.

5) URL

   Il est possible que si vous taper ```votredomain.fr/client``` il ne répond pas, dans ce cas. Créer un fichier ```.htaccess``` à la racine web (c'est à dire dans ```/public```).

   Apache : 
   ```
    Options +FollowSymLinks -Indexes
    RewriteEngine On

    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.php [L]
    ```
    Nginx : 
    ```
    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }
    ```

6) Permission

   Après l'installation du cms il est possible que le dosiser ```tmp`` ne puisse pas se créer. Il faudra donc donner la permission d'écriture, et de lecture.

7) Email

   Vous pouvez modifier les messages des emails vous acheter des packs de emails sur le marketplace. Pour utiliser le bon il suffit d'aller dans la configuration ( ```config/config.php```) Puis modifier la clée email.path.

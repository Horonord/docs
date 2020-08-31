### Accueil


## Introduction
![Logo](https://clientx.fr/assets/images/ClientXLight.png "ClientX")

[ClientX](https://clientx.fr/) est votre **copilote idéal dernière génération** qui a pour objectif de vous et votre entreprise aider au quotidiens dans l'hébergement de données, **gestion de client**, **facturation**, **taxes**, **création de service** et **paiement**.

ClientX s'utilise avec des **ressources** pour ajouter facilement des fonctionnalités et personnaliser entièrent votre espace client sans toucher aux sources accèsible facilement sur [notre market](https://clientx.fr/market). Grâce aux nombreux **modules** ajoutant des fonctionnalités complètes tels que la livraison automatique **Proxmox** ou le paiment par **PayPal** et bien plus !
Des **thèmes** communautaire sont disponibles pour tout les goûts et envie.

Les sources de ClientX ont été développés à la main sans framework PHP particulier. L'utilisation de [composer](https://getcomposer.org) pour les dépendences.

Dans cette documentation les informations important sur le fonctionnement du cms, la configuration en allant à la création de ressources et bien d'autre chose !

Vous pouvez modifier cette page via notre [github](https://github.com/clientXCMS) en proposant des pull requests. Si vous avez besoin d'aide ou une question. Contactez nous via notre [serveur discord](https://clientx.fr/discord) ou via le [support](https://clientx.fr/account/support).


**Prérequis**

**Modules préinstallés**
- Account
- Auth
- Admin
- Main
- Shop (comprennant les services)
- Support


**Installation**

1) Installer les dépendances via Composer

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

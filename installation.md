### Installation

## Prérequis

- PDO
- PHP 7.4+
- MySQL
- Extension GD/ImageMagick PHP
- Composer
- Extension JSON
- Extension ZP
- Réécriture d'URL

## Informations

Le CMS peut être installer sur un **serveur privée virtuel (VPS)**, **serveur dédié** ou **hébergement web**. Si vous utilisez les deux premières solutions, il sera sûrement nécéssaire d'installer vous même les prérequis.

## Modules préinstallés
- Account
- Auth
- Admin
- Main
- Shop
- Support


## Installation

#### 1) Installer les dépendances via Composer

   Pour installer, il suffit de faire la commande suivante dans le dossier ou ce trouve l'espace client : 
    ```composer.phar install --optimize-autoloader --no-dev```
    Si la commande ne fonctionne pas,  Installez [Composer](https://getComposer.org) et réessayer.

#### 2) Installation de la base de données

   Veuillez vous référer à cette [Page](https://clientx.fr/docs/database)

#### 3) Racine publique

   Pour des mesures de sécurité, le code est un crant plus bas que le dossier ```/public```. Il faut juste pointer votre hébergeur web sur ce bon dossier ou faire une configuration Apache ou Nginx. Voir "URL"

#### 4) Premier compte

   Pour créer votre premier *administrateur* il vous suffit de suivre le processus de création et d'accepter les EULA.
   
#### 5) URL

   Il est possible que si vous taper ```votredomain.fr/client``` il ne répond pas ou répond une erreur 404, dans ce cas. Créer un fichier ```.htaccess``` à la racine web.

   #### Apache :
   ```
    Options +FollowSymLinks -Indexes
    RewriteEngine On

    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.php [L]
   ```
   
   ##### Nginx :

   ```
    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }
   ```
#### 6) Permission

   Après l'installation de CLIENTX il est possible que le dosiser `tmp` ne puisse pas se créer. Il faudra donc donner la permission d'écriture, et de lecture.

#### 7) Email
   Vous pouvez modifier les messages des emails vous acheter des packs de emails sur le marketplace. Pour utiliser le bon il suffit d'aller dans la configuration ( ```config/config.php```) Puis modifier la clée email.path.

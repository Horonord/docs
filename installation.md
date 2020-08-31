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

## Installation des prérequis

Le CMS peut-être installer sur un **serveur privée virtuel (VPS)**, **serveur dédié** ou **hébergement web**. Si vous utiliser les deux premières solutions, il sera sûrement nécéssaire d'installer vous même **PHP**, **MySQL**, **Apache** ou **Nginx**. Voici des commandes pour l'installer.
```
apt update && apt upgrade
```
```
apt install apache zip curl
```
```
wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/php.list
apt update
apt install php7.4 php7.4-fpm php7.4-mysql php7.4-pgsql php7.4-sqlite php7.4-bcmath php7.4-mbstring php7.4-xml php7.4-curl php7.4-zip php7.4-gd
```

## Installation

1. Télécharger les sources de la dernière version de ClientX sur [notre site](https://clientx.fr).
2. Extraire l'archive à la racine de votre site web.
3. Mettre les droits d'écriture à la racine du serveur web.
```
chmod -R 755 /var/www/clientx
```
ou si l'utilisateur actuel n'est pas le même que celui du serveur web : 
```
chown -R www-data:www-data /var/www/azuriom
```
4. Installer les dépendances avec [Composer](https://getcomposer.org)
```
composer install
```
Pour une utilisation en production
```
composer install --optimize-autoloader --no-dev
```

5. Migrer la base de données
```
./vendor/bin/phinx migrate 
```
6. Seeder la base de données
```
./vendor/bin/phinx seed:run
```
7. Ajouter la tache CRON pour la boutique
```
*/0 0 * * * curl -s http://votredomaine.fr/store/cron > /dev/null
```
8. Ajouter le compte adminstrateur
Rendez vous sur votre site et suivez les étapes de création.

## Configuration du serveur web
### Apache 2
Si vous compter utiliser Apache 2, il peut-être nécéssaire d'activer la réécriture d'url. 
```
a2enmod rewrite
```

Ensuite modifier le fichier `/etc/apache2/sites-available/000-default.conf` et y ajouter ces lignes entre les balises `<VirtualHost>`

```
<Directory "/var/www/clientx">
    Options FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>
```
Puis redémarrer Apache pour que les modifications soit bien prise en compte.
```
service apache2 restart
```

### Nginx

Si selon vous Nginx c'est une meilleur solutions, vous pouvez configurer Nginx dans un site dans site-available`.

```
server {
    listen 80;
    server_name votredomain.com;
    root /var/www/clientx/public;
    index index.html index.htm index.php;

    charset utf-8;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }
    location = /favicon.ico { access_log off; log_not_found off; }
    location = /robots.txt  { access_log off; log_not_found off; }

    error_page 404 /index.php;

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
```

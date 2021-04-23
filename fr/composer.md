## Composer

Composer est essentiel pour **CLIENTXCMS**. 

## Installer les dépendances via Plesk

Rendez-vous dans votre hébergement, puis cliquez sur "PHP Composer".Plesk va trouver tout seul le ```package.json```, il ne sera donc que nécéssaire de cliquer sur Installer.

## Installation de Composer

Executez cette commande
```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```
Et vérifiez que la commande **`composer`** réponde correctement.
Pour plus d'informations à propos de composer : https://getcomposer.org/

## Installer les dépendances en cli

Assurez-vous d'avoir bien Composer d'installé sur machine, executez la commande `composer`. Si il ne trouve pas la commander. Installez Composer en vous aidant de la partie "Installation de composer"
Rendez-vous dans votre dossier où ce trouve CLIENTXCMS. 
Exécutez cette commande `composer install --optimize-autoloader --no-dev` ou adaptez-la pour convenir à votre situation.

Des messages "warning" devraient êtres affichés, pas d'inquiétude, cela impacte pas le CMS.

## Installation de Composer chez Ionos

Si vous êtes chez Ionos, l'installation est plus compliquée. 

Nous vous conseillons de suivre ce e[tutoriel](https://www.ionos.com/community/hosting/php/using-php-composer-in-11-ionos-webhosting-packages/) qui vous l'expliquera.

N'oubliez pas d'adapter la commande à votre version de php : si vous utilisez php 7.4 remplacez ```/usr/bin/php7.1-cli``` par ```/usr/bin/php7.4-cli``` et cela dans chaque commande.

Avant chaque commande **composer** ajoutez ```/usr/bin/php7.4-cli``` suivi d'un espace devant chaque commande (*adaptez la version de php*)
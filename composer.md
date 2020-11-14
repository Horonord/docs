## Composer

Composer est essentiel pour CLIENTXCMS. 

## Installer les dépendances via Plesk

Rendez-vous dans votre hébergement, puis cliquez sur "PHP Composer". à ce moment là, il va vous demander de rechercher le package.json en appuyant sur le bouton bleu. Vous cliquez, il devrait le trouver assez facilement. Puis cliquez sur le bouton "Installer" en haut à gauche.

## Installation de Composer

Executez cette commande
```shell
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```
Et vérifiez que la commande `composer` réponde correctement.
Pour plus d'informations : https://getcomposer.org/

## Installer les dépendances en cli

Assurez-vous d'avoir bien Composer d'installé sur machine, executez la commande `composer`. Si il ne trouve pas la commander. Installez Composer en vous aidant de la partie "Installation de composer"
Rendez-vous dans votre dossier où ce trouve CLIENTXCMS. 
Exécutez cette commande `composer install --optimize-autoloader --no-dev` ou adaptez-la pour convenir à votre situation.

Des messages "warning" devraient êtres affichés, pas d'inquiétude, cela impacte pas le CMS.
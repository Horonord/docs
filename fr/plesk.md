# Module Plesk

## Installation

Pour installer le module plesk, il vous suffit de transférer les fichiers correspondants dans **/src/**, **/views/** et **/Themes/**.

<br>Une fois cela fait, le module s'ajoutera tout seul dans le CMS. 
<br> **Si ce n'est pas le cas**, il vous suffit d'ajouter la ligne suivante : <br>```->addModule(App\NomDuModule\NomDuModuleModule::class)```

Il faut aussi installer **php-xml** en faisait la commande : ```apt install php-xml```.

## Ajout de dépendances

Pour le bon fonctionnement du CMS avec le module Plesk, il vous suffit d'ajouter la ligne suivante au fichier **composer.json** : 
```"plesk/api-php-lib": "^1.0.7"```. 

Cela ressemblera à cela : 

![image](https://media.discordapp.net/attachments/585094063204728832/835999899786018846/unknown.png)

Puis faites un **composer install** ou cliquez sur Install depuis Plesk (si vous utilisez plesk).

## Création d'un Produit 

Lorsque vous créez un Produit, vous avez le choix entre **Plesk Hosting** et **Plesk Reseller**

**Plesk Hosting** : C'est un Hébergement WEB simple.

**Plesk Reseller** : C'est un Revendeur WEB.

Après cela, vous devez choisir entre les "**Plans**" que vous avez créés **au préalable** sur votre panel Plesk, sinon, vous ne verrez rien.

![image](https://media.discordapp.net/attachments/585094063204728832/836002184134262834/unknown.png)

## Fin de la Configuration

Comme pour tous les modules, il faut a la fin se rendre dans **Database** puis cliquer sur **MIGRATE**.
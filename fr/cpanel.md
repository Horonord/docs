# Module Cpanel

## Installation

Pour installer le module cPanel, il vous suffit de transférer les fichiers correspondants dans **/src/**, **/views/** et **/Themes/**.

<br>Une fois cela fait, le module s'ajoutera tout seul dans le CMS.
<br> **Si ce n'est pas le cas**, il vous suffit d'ajouter la ligne suivante : <br>```->addModule(App\NomDuModule\NomDuModuleModule::class)```

## Création d'un Produit

Lorsque vous créez un Produit, vous avez le choix entre **Plesk Hosting** et **Plesk Reseller**

**cPanel Hosting** : C'est un Hébergement WEB simple.

**cPanel Reseller** : C'est un Revendeur WEB.

Après cela, vous devez choisir entre les "**Plans**" que vous avez créés **au préalable** sur votre cPanel, sinon, vous ne verrez rien.

**Attention, tous les "Plans" sont mélangés entre eux : c'est à dire que les plans Reseller et Hosting ne sont pas différenciés !**

![image](https://media.discordapp.net/attachments/585094063204728832/836003300784603176/unknown.png)

## Fin de la Configuration

Comme pour tous les modules, il faut a la fin se rendre dans **Database** puis cliquer sur **MIGRATE**.
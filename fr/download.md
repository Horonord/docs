# Module de téléchargements

## Installation

Pour installer le module Download, il vous suffit de transférer les fichiers correspondants dans **/src/**, **/views/** et **/Themes/**.

<br>Une fois cela fait, le module s'ajoutera tout seul dans le CMS.
<br> **Si ce n'est pas le cas**, il vous suffit d'ajouter la ligne suivante : <br>```->addModule(App\NomDuModule\NomDuModuleModule::class)```

## Création d'un Serveur

Pour ce module, il n'y a aucunement besoin de créér un serveur.

## Dépendances

Pour le bon fonctionnement du CMS avec le module Download, il vous suffit d'ajouter la ligne suivante au fichier **composer.json** :
```"symfony/http-foundation": "^5.2"```.

Cela ressemblera à cela : ![image](https://media.discordapp.net/attachments/585094063204728832/836006059440996392/unknown.png)

## Clef GitHub

Si votre dépot GitHub est privé, il vous faudrat ajouter cette ligne dans le .env :

```GITHUB_AUTH_TOKEN=VOTRETOKEN```

Vous pouvez générer une clef API GitHub [ici](https://github.com/settings/tokens).

**Attention, le token ne sera affiché qu'une seule fois !**

## Fin de la Configuration

Comme pour tous les modules, il faut a la fin se rendre dans **Database** puis cliquer sur **MIGRATE**.
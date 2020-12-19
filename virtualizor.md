### Virtualizor

## Introduction

Virtualizor est un panel de gestion qui permet de créér des serveurs VPS, grâce à ce module, vous pouvez automatiser la création et la gestion des VPS. [Site de Virtualizor](https://virtualizor.com)

## Mise en Place de Virtualizor

La mise en place de Virtualizor est très simple : il vous suffit de vous rendre sur votre **Panel Virtualizor** puis de vous rendre dans Configuration puis Server Info et vous pourrez récupérer vos informations API.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/virtualizor/api.png "Panel - API")

## Intégration à ClientX

Une fois que **Virtualizor** est configuré, il suffit de l'intégrer à ClientX est c'est la partie la plus simple ! 

Il vous suffit de télécharger le module Virtualizor sur [Le Marketplace](https://clientx.fr/market) (*préalablement acheté*).

Vous avez juste à glisser les fichiers téléchargés dans la racine de votre hébergement WEB *(liste des hébergeurs officiellement compatibles [ici](https://clientx.fr/docs/installation)*.

Pour le fichier views, il faut se rendre dans ```Themes``` puis dans votre Thème (**de base, c'est Start**) puis glissez ```views```.

Il faudrat ajouter la ligne ```->addModule(App\Virtualizor\VirtualizorModule::class)``` dans index.php.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/virtualizor/index.png "Index")

Actualisez la page de votre panel admin ClientX et l'option Virtualizor apparaîtra dans les options de création des offres, il vous suffira juste de créer les offres.

## Conclusion

Et voilà, Facile, n'est-ce pas ? Vous êtes prêt à utiliser **Virtualizor** avec **ClientX** ! 

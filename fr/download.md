# Module de téléchargements
Le module de téléchargement permet de pouvoir télécharger des fichiers ou dépot github à vos clients.

*Note* : Ce module n'est pas fourni par default, pour plus de détails :  [cliquez ici](https://clientxcms.com/app/Cpanel)
*Note 2*: Pour plus d'informations sur l'installation du module, [cliquez-ici](https://clientxcms.com/docs/fr/modules)
## Création de produit
Avant tout, il faut que le module soit activé pour créer un produit
Pour créer un produit, allez dans `Espace d'administration` > `Boutique` > `Produits` > `Nouveau`
Vous devez sélectionner le type `Download` pour le produit.
Après ceci, vous serez redirigé vers la page de configuration.
Vous ajouteriez le chemin vers le fichier téléchargeable et un nom.


## Clef GitHub

Si votre dépot GitHub est privé, il vous faudra ajouter cette ligne dans le fichier `.env` :

```GITHUB_AUTH_TOKEN=VOTRETOKEN```

Vous pouvez générer une clef API GitHub [ici](https://github.com/settings/tokens).

**Attention, le token ne sera affiché qu'une seule fois !**

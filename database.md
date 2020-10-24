### Base de données

## Introduction 
Pour stocker les données, CLIENTX utilise le système relationnel MySQL. Une base est obligatoire (vierge ou non) pour contenir les tables nécessaires au CM. PDO (PHP Data Objets) est utilisé pour interagir avec la base. Il faut donc que l'extension ainsi que PDO MySQL soit installé sur votre système.

## Connection
Les informations de connection à la base sont demandés dans le ```.env```. Ce fichier ne doit pas être versionner. Voici un exemple
```
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=clientx
DB_USERNAME=root
DB_PASSWORD=root
DB_CHARSET=utf8
```
## Tester la connection

Pour vérifier que la connection entre CLIENTX et MySQL soit bien opérationnelle. Ouvrez une page de l'application :
Si la page vous renvoi le message d'erreur :
`Erreur de connexion à la base de données` la connection n'a pas eu lieu. Pour plus de détails activez dans le ```.env``` le mode debug (APP_DEBUG) à "true".
Attention, les identifiants peuvent apparaitre sur la page. Mais ça peut vous aider a résoudre le problème.

## Migration

Pour gérer les migrations de la base de données (pour le développement ou la mise en production). ClientXCMS utile [phinx.org](https://phinx.org/). Vous pouvez vous référer a leur documentation pour approfondir sur son fonctionnement.

### Commandes importantes 
- Migrate
    
    Cette commande permet de migrer les migrations manquantes.
    ```./vendor/bin/phinx migrate```

- Create
    Cette commande est importante en développement, elle permet de créer une migration.
    ```./vendor/bin/phinx create PremièreMigration```
- Seed
    Cette commande permet de remplir votre base avec des données prêt définit ou générer dynamiquement via la librairie [faker](https://github.com/fzaninotto/Faker)
    ```./vendor/bin/phinx seed:run```
    ou
    ```./vendor/bin/phinx seed:create PremierSeeding```


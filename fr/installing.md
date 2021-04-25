# Installer CLIENTXCMS

### Téléchargement CLIENTXCMS

Pour télécharger CLIENTXCMS : 
1. Connectez-vous sur votre espace client
2. Sur votre tableau de bord, cliquez sur "Téléchargement"
3. Cliquez sur l'icone de nuage pour télécharger la dernière version.

### Téléchargement de version antérieur

Pour télécharger une version antérieure de CLIENTXCMS, ouvrez une demande pour télécharger la version.

### Création de base de données
CLIENTXCMS utilise MySQL® pour sauvegarder les données. Vous pouvez en créer une lors de l'installation ou après. [Plus d'informations](https://clientxcms.com/docsc/fr/database)

- [Création de base de données dans cPanel & WHM](https://docs.cpanel.net/cpanel/databases/mysql-database-wizard/)
- [Création de base de données dans Plesk](https://docs.plesk.com/en-US/17.0/customer-guide/advanced-website-databases.69535/)
### Privilège de la base de données
Les privilèges suivants sont requis :
- DELETE
- INSERT
- UPDATE
- LOCK TABLES

Pour l'installation, mise à jours, activation / désactivation de module demande les privilèges suivants : 
- ALTER
- CREATE
- DROP
- INDEX

### Installation de CLIENTXCMS

Pour installer CLIENTXCMS, vous pouvez suivre ce processus : 
- Unzip l'archive dans un dossier sur votre ordinateur
- Renomer le fichier `.env.copy` en `.env`
- Télécharger les dépendances via composer
- Remplir le `.env` avec les identifiants de la base de données
- Ouvrez votre navigateur et rendez-vous sur https://domaine.fr/install pour lancer l'installation.
- Entrez les informations du compte administrateur "propriétaire" et entrez votre clé de licence.
Après ceci, vous serrez automatiquement connecté sur le panel d'administration.
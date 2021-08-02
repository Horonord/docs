# Installer CLIENTXCMS

### Téléchargement CLIENTXCMS

Pour télécharger CLIENTXCMS : 
1. Connectez-vous sur votre espace client
2. Sur votre tableau de bord, cliquez sur "Téléchargement"
3. Choisisiez le téléchargement commençant par "CLIENTXCMS". Ce sera la dernière version de sortie

### Téléchargement de version antérieur

Pour télécharger une version antérieure de CLIENTXCMS, ouvrez une demande pour télécharger la version demandées.

### Création de base de données
CLIENTXCMS utilise MySQL® pour sauvegarder les données. Vous pouvez en créer une lors de installation ou après. [Plus d'informations](https://clientxcms.com/docs/fr/database)

- [Création de base de données dans cPanel & WHM](https://docs.cpanel.net/cpanel/databases/mysql-database-wizard/)
- [Création de base de données dans Plesk](https://docs.plesk.com/en-US/17.0/customer-guide/advanced-website-databases.69535/)
### Privilège de la base de données
Les privilèges suivants sont requis :
- DELETE
- INSERT
- UPDATE
- LOCK TABLES
- ALTER
- CREATE
- DROP
- INDEX

### Installation de CLIENTXCMS

Pour installer CLIENTXCMS, vous pouvez suivre ce processus : 
- extract de l'archive dans un dossier sur votre ordinateur
- Renomer le fichier `.env.copy` en `.env`
- Télécharger les dépendances via [composer](https://clientxcms.com/docs/fr/composer)
- Remplir le `.env` avec les identifiants de la base de données
- Modifier la racine du serveur web 
- Ouvrez votre navigateur et rendez-vous sur [https://domain.fr](https://domain.fr) pour lancer l'installation.
- Entrez les informations du compte administrateur "propriétaire" et entrez votre clé de licence.
Après ceci, vous serrez automatiquement connecté sur le panel d'administration.
  
### Modifier la racine du serveur web
Par mesure de sécurité, la racine du serveur pointe vers le dossier `/public` de CLIENTXCMS.
- [Modification de la racine du serveur web dans plesk](https://docs.plesk.com/fr-FR/onyx/administrator-guide/h%C3%A9bergement-web/structure-des-r%C3%A9pertoires-de-sites-web/d%C3%A9finir-une-racine-du-document-personnalis%C3%A9e.77500/)
![image](https://docs.plesk.com/fr-FR/onyx/administrator-guide/images/77501.webp)
  Sur l'interface cPanel, dans la partie domaine (ou sous-domaine), dans la colonne des racines web
  ![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/fr/images/cpanel/cpanel.png)

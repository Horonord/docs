## Changer la racine du document

Pour plus de sécurité, comme la plupart des frameworks actuel, CLIENTXCMS a sa racine dans le dossier `/public`.

### Changer depuis plesk
La documentation officielle de plesk fournit un article sur la [Modification de la racine du serveur web dans plesk](https://docs.plesk.com/fr-FR/onyx/administrator-guide/h%C3%A9bergement-web/structure-des-r%C3%A9pertoires-de-sites-web/d%C3%A9finir-une-racine-du-document-personnalis%C3%A9e.77500/)
  ![image](https://docs.plesk.com/fr-FR/onyx/administrator-guide/images/77501.webp)

**Exemple** : `exemple.fr/public`

### Changer depuis cPanel

Sur l'interface cPanel, dans la partie domaine (ou sous-domaine), dans la colonne des racines web
![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/fr/images/cpanel/cpanel.png "Cpanel")

## Changer via Apache

Pour modifier la racine avec un serveur web Apache, allez dans le dossier `/etc/apache2/sites-available/` et ouvrez le fichier `00-default.conf`. Enfin changez le "Document Root" en y ajoutant `/public`.

**Exemple :**
```bash
<VirtualHost *:8080>
    ServerAdmin user@localhost
    DocumentRoot /var/www/clientxcms/public
</VirtualHost>
```

Enfin, relancez votre serveur apache pour que vos modifications soient prises en compte.

```sudo service apache2 restart```
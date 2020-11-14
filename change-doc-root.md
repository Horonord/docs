## Changer la racine du document

Pour plus de sécurité, CLIENTXCMS a sa racine dans le dossier `/public`. Ce qui est pas fait par defaut dans un hébergement web classique.

### Changer depuis plesk

Pour modifier la racine depuis plesk, Cliquez sur "Hébergement & DNS" ("Hosting & DNS" en anglais) puis "Paramètres d'hébergement" ("Hosting settings" en anglais). 
Sur cette page, vous pourrez modifier la racine du document en ajoutant `/public` à la suite puis cliquez sur "appliquer" ou "Apply" en anglais.
Exemple : clientarea.clientx.fr/public

## Changer via Apache

// n /etc/apache2/sites-available/ open the 000-default.conf file, and change the Document Root to the absolute path of your directory.
Pour modifier la racine avec un serveur web Apache, Allez dans le dossier `/etc/apache2/sites-available/` et ouvrez le fichier `00-default.conf`. Enfin changez le "Document Root" en ajoutant `/public`
Exemple : 
<VirtualHost *:8080>
    ServerAdmin user@localhost
    DocumentRoot /var/www/clientx/public
</VirtualHost>


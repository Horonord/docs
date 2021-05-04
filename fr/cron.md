# Tâches Crons

## Setup dans le Cas d'un VPS

Il vous suffit de vous connecter en SSH au VPS puis de faire la commande ```crontab -e```.

Puis d'ajouter la ligne suivante : ```* * * * * php /var/www/clientxcms/Cron/index.php >> /dev/null 2>&1```

## Si vous êtes sur Plesk 

Si vous êtes sur Plesk, vous devez vous rendre dans **Scheduled Tasks** puis script php et mettre la direction de /Cron/index.php



# Tâches récurrentes
Les tâches récurrentes permettent de livrer les services, expirer les services ou tout simplement faire des actions régulières sur CLIENTXCMS. 
## Page de rapport 
Une page de rapport dédiée est disponible pour chaque action CRON de CLIENTXCMS. Elles sont disponibles sur votre  `Espace d'administration` > `Rapport` > `Tâches CRON` et montrent chaque execution de la tâche demandée.
![img](https://media.discordapp.net/attachments/598633976768364544/860289527163256832/unknown.png)
Pour plus de détails sur une execution vous pouvez cliquer sur le bouton bleu dans chaque ligne du tableau et vous pourrez voir l'exception déclenchée ou le resultat de la tâche.

## Execution manuelle
Dans la page expliquée plus haut, vous pouvez exécuter une tâche manuellement en cliquant sur le bouton bleu en bas de page.

## Suppression des anciennes executions
Les historiques peut être lourd dans la base de données, vous pouvez supprimer les plus anciens et gardez uniquement l'historique des 15 derniers jours d'activité.

## Configuration sur un VPS/Dédié
- Connecter en SSH au VPS/Dédié
- Executez la commande `crontab -e`
- Ajouter une ligne ```* * * * * php /var/www/clientxcms/Cron/index.php >> /dev/null 2>&1```

Avec cette ligne, les tâches effectuerons toutes les minutes. Mais vous pouvez augmenter le temps entre deux executions pour soulager le serveur.
## Configuration sur plesk
- Connecter à votre interface plesk
- Aller dans `Outils & Paramètres` > `Tâches planifiés` > `Ajouter une tâche`
- Sélectionnez le type de tâche "Execute un script PHP"
- Choisissez-le fichiez `/Cron/index.php` (aucun argument requis)
- Utilisez la version de php 7.4.X (attention cela peut poser des problèmes si la version est inférieur)
- Dans "Run", Sélectionnez `Cron style` et `*/1 * * * *`

![img](https://media.discordapp.net/attachments/598633976768364544/860287152838672394/unknown.png)

**Information** : certains hébergeurs peuvent désactiver les tâches récurrentes, renseignez-vous avant pour demander leurs de les activer.
# Tâches récurrentes
Les tâches récurrentes permettent de livrer les services, faire expirer les services ou tout simplement faire des actions régulières sur CLIENTXCMS. 
## Page de rapport 
Une page de rapport dédiée est disponible pour chaque action CRON de CLIENTXCMS. Elles sont disponibles sur votre  `Espace d'administration` > `Rapport` > `Tâches CRON` et montrent chaque execution de la tâche demandée.
![img](https://media.discordapp.net/attachments/598633976768364544/860289527163256832/unknown.png)
Pour plus de détails sur une execution vous pouvez cliquer sur le bouton bleu dans chaque ligne du tableau et vous pourrez voir l'exception déclenchée ou le resultat de la tâche.

## Execution manuelle
Dans la page expliquée plus haut, vous pouvez exécuter une tâche manuellement en cliquant sur le bouton bleu en bas de page.

## Suppression des anciennes executions
Les historiques peuvent être lourds dans la base de données, vous pouvez supprimer les plus anciens et garder uniquement l'historique des 15 derniers jours d'activité.

## Configuration sur un VPS/Dédié
- Connectez-vous en SSH au VPS/Dédié
- Executez la commande `crontab -e`
- Ajoutez une ligne ```* * * * * php /var/www/clientxcms/Cron/index.php >> /dev/null 2>&1```

Avec cette ligne, les tâches s'effectueront toutes les minutes. Mais, vous pouvez augmenter le temps entre deux executions pour soulager la charge du serveur.

## Configuration sur plesk
- Connectez-vous à votre interface plesk
- Allez dans `Outils & Paramètres` > `Tâches planifiées` > `Ajouter une tâche`
- Sélectionnez le type de tâche "Execute un script PHP"
- Choisissez le fichiez `/Cron/index.php` (aucun argument requis)
- Utilisez la version de php 7.4.X (attention cela peut poser des problèmes si la version est inférieure)
- Dans "Run", sélectionnez `Cron style` et `*/1 * * * *`

![img](https://media.discordapp.net/attachments/598633976768364544/860287152838672394/unknown.png)

**Information** : certains hébergeurs peuvent désactiver les tâches récurrentes, renseignez-vous avant pour leur demander de les activer.

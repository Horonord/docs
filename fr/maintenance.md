
## Maintenance
CLIENTXCMS introduit un système permettant de mettre l'espace client en maintenance et bloquant l'accès aux utilisateurs non autorisés.
Pour gérer la maintenance, allez dans votre `Espace d'administration` > `Paramètres` > `Maintenance`.


**Information** : Les services fonctionneront toujours normalement, les utilisateurs ne pourront plus se connecter à leur compte client.
### Activation
Pour activer la maintenance, cochez la checkbox 'Enable maintenance', les détails de la maintenance apparaitrons.
Puis, sauvegardez vos modifications en appuyant sur "Sauvegarder"
Champs :
- Message | *Titre informatif, pour expliquer à vos utilisateurs la raison de la maitenance*
- Début | *Permet de renseigner le début de la maintenance*
- Fin | *Permet de renseigner la fin de la maintenance (ne sera pas affichée sur la page)*
- URL | *URL permettant de passer à travers la maintenance et utiliser l'espace client classiquement*

L'URL doit rester secrète aux yeux de vos clients. 
![Image](https://media.discordapp.net/attachments/598633976768364544/860274528576208896/unknown.png)

### Désactivation 

Pour désactiver la maintenance, décochez la checkbox 'Enable maintenance', les détails de la maintenance dispparaitrons.
Puis, sauvegardez vos modifications en appuyant sur "Sauvegarder".

### Modifier la vue de maintenance
Par default, les thèmes fournis la template de maintenance pour la modifier : `/Themes/NomThemes/403.twig`

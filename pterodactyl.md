### Pterodactyl

## Introduction
[Pterodactyl](https://pterodactyl.io) est un panel de gestion et de création de serveurs de Jeux.

## Mise en Place de Pterodactyl

Pout mettre en place pterodactyl sur votre serveur dédié ou VPS (Virtual Private Server), il suffit de suivre le tutoriel pour installer [le panel](https://pterodactyl.io).

Une fois cela fait, vous pouvez passer à l'étape suivante.

## Modifier la configuration par défaut des serveurs

Pour modifier la configuration des serveurs de jeux de base, il vous suffit de vous rendre dans ```src/Pterodactyl/AbstractManager.php``` et de modifier la propriété ```$defaultsFields```.

## Intégration à ClientX

Une fois que Pterodactyl est configuré, il suffit de rentrer les deux clefs API et le lien de votre panel.

Sauvegardez et ClientX se connectera automatiquement à Pterodactyl.

Pour trouver la clef API Utilisateur il faut se rendre dans ```/account/api``` et dans les paramètres API du panel admin pour l'autre clef.

## Prise en compte par ClientX

Pour que le module fonctionne parfaitement, il faut vous rendre dans votre espace administration puis dans ```Base de données``` puis cliquez sur ```Migrate```.

Le module sera ajouté dans la Base de Données de ClientX.

## Conclusion

Et voilà, Facile, n'est-ce pas ? Vous êtes prêt à utiliser **Pterodactyl** avec **ClientX** ! 

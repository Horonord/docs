### Pterodactyl

## Introduction
[Pterodactyl](https://pterodactyl.io) est un panel de gestion et création de serveurs de Jeux très utilisé dans le monde de l'hébergement basé sur le Framework PHP Laravel. Le Module Pterodactyl est par défaut inclus dans le CMS, en cas contraire, vous pouvez le télécharger sur le market. 

## Mise en Place de Pterodactyl

Pout mettre en place pterodactyl sur votre serveur dédié ou VPS (Virtual Private Server), il suffit de suivre le tutoriel pour installer [le panel](https://pterodactyl.io). Nous proposerons également des options adaptées pour que notre équipe installe le pterodactyl pour vous d'ici peu de temps.
Une fois cela fait, vous pouvez passer à l'étape suivante.

## Modifier la configuration par défaut des serveurs

Pour modifier la configuration des serveurs de jeux de base, il vous suffit de vous rendre dans ```src/Pterodactyl/AbstractManager.php``` et de modifier la propriété ```$defaultsFields```.

## Intégration à ClientX

Une fois que Pterodactyl est configuré, il suffit de rentrer les deux clefs API et le lien de votre panel.

Sauvegardez et ClientX se connectera automatiquement à Pterodactyl.

Pour trouver la clée API Utilisateur il faut se rendre dans ```/account/api``` et dans les paramètres API du panel admin pour l'autre clée.

## Conclusion

Et voilà, Facile, n'est-ce pas ? Vous êtes prêt à utiliser **Pterodactyl** avec **ClientX** ! 

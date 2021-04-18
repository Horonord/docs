### Paramétrer l'envoi d'e-mails

## Introduction

L'envoi de mails automatisé est une fonction incontournable de ClientX, vous voyez-vous envoyer les mails un à un à vos clients avec leurs factures, leurs identifiants etc... ? 
Eh bien, non, chez ClientX, nous automatisons tous les envois de mail. Une fois configurés, aucune action ne sera requise de votre part. Si vous ne souhaitez pas les configurer, les e-mails seront envoyés via **PhpMail**.

## Récupérer ses serveurs SMTP

# Via Plesk

Connectez-vous au panneau Plesk.

Allez dans la partie 'Mail'.

Cliquez sur l'icone d'informations à côté de votre adresse E-Mail.

Les noms de vos serveurs de messagerie entrants et sortants seront affichés ici.

# Via Cpanel

Connectez-vous au panneau cPanel.

Allez dans la partie 'Comptes de messagerie', puis dans l'onglet 'Comptes de messagerie'.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/mail/cpanel1.png "Configuration Mail")

Cliquez sur le boutton 'Connect Device'.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/mail/cpanel2.png "Configuration Mail")

Les noms de vos serveurs de messagerie entrants et sortants seront affichés ici.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/mail/cpanel3.png "Configuration Mail")

## Les Ports SMTP

Les ports non sécurisés par défaut sont le port 25 et le port 587, tandis que le port 465 est utilisé pour le SMTP sécurisé.

Nous vous recommandons d'utiliser le port sécurisé soit avec le certificat fourni par Plesk ou cPanel, soit avec votre certificat SSL personnalisé.

Nous **recommandons vivement** d'utiliser le protocole **SMTP** pour éviter les envois d'emails en **SPAM** et une meilleure sécurisation de l'envoi ainsi que l'utilisation de mot de passe sécurisé.

Si l'option est désactivée, l'e-mail sera envoyé avec la fonction mail de php.

## Connexion à ClientX 

Pour connecter votre serveur SMTP à ClientX, il vous suffit d'aller dans l'administration de ClientXCMS, dans paramétres et d'aller dans **E-Mail**.

Vous n'aurez plus qu'à rentrer vos serveurs et cliquez sur ```Tester la connexion```. 

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/mail/config.png "Configuration Mail")

Si vous recevez bien un mail sur l'adresse email renseignée au dessus, c'est que tout fonctionne.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/mail/mail.png "Mail de Vérification")
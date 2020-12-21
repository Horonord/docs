### Paramétrer l'envoi de Mails

## Introduction

L'envoi de mails automatisé est une fonction incontournable de ClientX, vous voyez-vous envoyer les mails un à un à vos clients avec leurs factures, leurs identifiants etc... ? 
Eh bien, non, chez ClientX, nous automatisons tous les envois de mail. Une fois configurés, aucune action ne sera requise de votre part.

## Récuprérer ses serveurs SMTP

# Via Plesk

Connectez-vous au panneau Plesk.

Allez dans la partie 'Mail'.

Cliquez sur l'icone d'informations à côté de votre adresse E-Mail.

Les noms de vos serveurs de messagerie entrants et sortants seront affichés ici.

# Via Cpanel

Connectez-vous au panneau cPanel.

Allez dans la partie 'Comptes de messagerie', puis dans l'onglet 'Comptes de messagerie'.

Cliquez sur le boutton 'Connect Device'.

Les noms de vos serveurs de messagerie entrants et sortants seront affichés ici.

## Les Ports SMTP

Les ports non sécurisés par défaut sont le port 25 et le port 587, tandis que le port 465 est utilisé pour le SMTP sécurisé.

Nous vous recommandons d'utiliser le port sécurisé soit avec le certificat fourni par Plesk ou cPanel, soit avec votre certificat SSL personnalisé.

Nous **recommandons vivement** d'utiliser le protocole **SMTP** pour éviter les envois d'emails en **SPAM** et une meilleure sécurisation de l'envoi ainsi que l'utilisation de mot de passe sécurisé.

Si l'option est désactivée, l'e-mail sera envoyé avec la fonction mail de php.
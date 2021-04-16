### Stripe

## Introduction

Stripe est un service de paiement vous permet d'accepter les paiements par carte bancaire directement sur ClientXCMS via [Site de Stripe](https://stripe.com). Pour informations, les informations bancaire sont stockées a distance par Stripe. ClientXCMS sauvegarde uniquement le StripeID d'un client, aucune données sensible dans sa base de données. Egalement prenez consience de leur politique de litige et les différents conditions d'utilisatation de celui-ci. 

## Mise en Place de Stripe

La mise en place de Stripe est très simple : il vous suffit de vous rendre sur votre [Dashboard Stripe](https://dashboard.stripe.com/dashboard) puis de créér des identifiants API.

Un Webhook Stripe est aussi nécéssaire à la mise en place de Stripe sur ClientX, pour cela rendez-vous dans la [gestion des webhook](https://dashboard.stripe.com/webhooks) puis crééz en un nommé ClientX (par exemple).

Dans URL d'endpoint il suffit de mettre : ```votredomaine/api/stripe``` (https://demo.clientx.fr/api/stripe).

La description est facultative.

Il faudrat aussi ajouter ces 3 options dans évènements à envoyer : ```checkout.session.completed``` ```checkout.session.async_payment_succeeded``` ```checkout.session.async_payment_failed```.

## Intégration à ClientX

Une fois que Stripe est configuré, il suffit de l'intégrer à ClientX est c'est la partie la plus simple ! 

Il vous suffit de télécharger le module Stripe sur [Le Marketplace](https://clientx.fr/market) (*préalablement acheté*).

Vous avez juste à glisser les fichiers téléchargés dans la racine de votre hébergement WEB (liste des hébergeurs officiellement compatibles [ici](https://clientx.fr/docs/installation)).

Il faudrat ajouter la ligne ```addModule(App\Stripe\StripeModule::class)``` dans l'index.php situé dans /public.

Actualisez la page de votre panel d'administration ClientXCMS et l'option Stripe apparaîtra dans les options Administrateurs, il vous suffira juste de remplir les champs avec : la Clée Stripe, le Secret du Client Stripe et le Secret de l'ENDPOINT Stripe générés au préalable. 
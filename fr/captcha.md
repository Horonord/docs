### Configuration du Captcha

## Introduction

Le CAPTCHA, vous le conaissez sûrement, il sert à sécuriser votre site contre les attaques ou les tentatives de créations de comptes en masse par des robots.

Généralement, il se présente sous forme d'une case à cocher et d'images à sélectionner pour les plus complexes.

## Mise en Place du Recaptcha de Google

Premièrement, rendez-vous sur la [console google](https://www.google.com/recaptcha/admin/)  puis [crééz un site](https://www.google.com/recaptcha/admin/create).

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/captcha/recaptcha/registration.png "Création")

Une fois votre site enregistré, les clef API devraient apparaître. 

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/captcha/recaptcha/registered.png "Créé")

Vous pouvez vous rendre dans ClientX puis ajouter ces informations dans **ReCaptcha**.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/captcha/recaptcha/recapatcha.png "ClientX")

Le champ ```  E-Mail bannis ou domaine a l'inscription ``` est **factultatif**, il sert à bannir des domaines précis ou une adresse précise du Captcha.

## Mise en Place du Hcaptcha

Premièrement, rendez-vous sur le [dashboard hcaptcha](https://dashboard.hcaptcha.com/overview) et allez sur [nouveau site](https://dashboard.hcaptcha.com/sites/new).

Remplissez les informations, choisissez la difficulté et cliquez sur **Sauvegarder**.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/captcha/Hcaptcha/registering.png "Création")

Une fois votre site enregistré, vous aurez accès à votre **site key**. 

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/captcha/Hcaptcha/registered.png "Créé")

Pour trouver votre **Clef Secrète**, rendez-vous dans **Paramètres** de votre compte et vous trouverez la clef secrète.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/captcha/Hcaptcha/secret.png "Le Secret")

Vous pouvez vous rendre dans ClientX puis ajouter ces informations dans **HCaptcha**.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/captcha/Hcaptcha/hcaptcha.png "ClientX")

Le champ ```  E-Mail bannis ou domaine a l'inscription ``` est **factultatif**, il sert à bannir des domaines précis ou une adresse précise du Captcha.

## Conclusion

Maintenant, vous pouvez utiliser le **Captcha** avec **ClientX** !
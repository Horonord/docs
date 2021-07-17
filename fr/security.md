# Sécurité
La sécurité est importante, pour configurer les captchas allez dans `Espace d'administration` > `Paramètres` > `Security`.
## Mise en Place du Recaptcha de Google

Premièrement, rendez-vous sur la [console google](https://www.google.com/recaptcha/admin/)  puis [crééz un site](https://www.google.com/recaptcha/admin/create).

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/fr/images/captcha/recaptcha/registration.png "Création")

Une fois votre site enregistré, les clef API devraient apparaître.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/fr/images/captcha/recaptcha/registered.png "Créé")

Vous pouvez vous rendre dans ClientX puis ajouter ces informations dans **ReCaptcha**.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/fr/images/captcha/recaptcha/recapatcha.png "ClientX")

## Mise en Place du Hcaptcha

Premièrement, rendez-vous sur le [dashboard hcaptcha](https://dashboard.hcaptcha.com/overview) et allez sur [nouveau site](https://dashboard.hcaptcha.com/sites/new).

Remplissez les informations, choisissez la difficulté et cliquez sur **Sauvegarder**.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/fr/images/captcha/Hcaptcha/registering.png "Création")

Une fois votre site enregistré, vous aurez accès à votre **site key**.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/fr/images/captcha/Hcaptcha/registered.png "Créé")

Pour trouver votre **Clef Secrète**, rendez-vous dans **Paramètres** de votre compte et vous trouverez la clef secrète.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/fr/images/captcha/Hcaptcha/secret.png "Le Secret")

Vous pouvez vous rendre dans ClientXCMS puis ajouter ces informations dans **HCaptcha**.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/fr/images/captcha/Hcaptcha/hcaptcha.png "ClientX")


## Email bannis

Le champ ```  E-Mail bannis ou domaine a l'inscription ``` est **factultatif**, il sert à bannir des domaines précis ou une adresse précise séparés par une virgule de l'inscription.

*Note* : Il ne supprimera pas les utilisateurs avec ces emails.

## Personnel
L'espace d'administration est sécurisé par un système d'authentication par des comptes autorisés avec un mot de passe et un email.
Vous pouvez ajouter des autorisations à votre personnel (support, développeur, technicien) en allant dans votre `Espace d'administration` > `Personnel`.

### Accès propriétaire

Cette permission est la plus haute possible, elle permet de gérer totalement les accès (y compris la suppression de comptes). Il est conseillé de mettre un seul compte propritaire pour éviter tout problème.
CLIENTXCMS et son personnel ne sont aucunement responsable de perte d'accès.

### Modifier le mot de passe quand il y a qu'un seul accès
- Connectez-vous à la base de données MySQL (ex: phpmyadmin)
- Générez le hash du mot de passe depuis https://www.bcrypt.fr/
- Executez cette requête SQL pour modifier le mot de passe 
`UPDATE admins SET password = 'HashDuMotdepass'`
  
Vous pourrez maintenant vous connecter avec le mot de passe généré au préalable.

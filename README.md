# Distribution
Fichiers nécessaires au fonctionnement du launcher

# Comment modifier ?
Plutôt simple, d'abord cloner le repo (`git clone https://github.com/MineCityLife/Distribution`), ensuite ajouter/modifier/supprimer les fichiers selon la hiérarchie suivante :

`/servers/MineCityLifeRP-1.7.10/forgemods/required` : Les mods requis pour jouer sur le serveur
`/servers/MineCityLifeRP-1.7.10/forgemods/optionalon` : Les mods optionels qui peuvent être désactivés par le joueur mais qui sont par défaut activés
`/servers/MineCityLifeRP-1.7.10/forgemods/optionaloff` : Les mods optionels qui peuvent être activés par le joueur mais qui sont par défaut désactivés
`/servers/MineCityLifeRP-1.7.10/files/` : Les fichiers qui seront installés dans le dossier équivalent du .minecraft du joueur (par exemple les configurations de mods, etc.)
`/servers/MineCityLifeRP-1.7.10/libraries/` : Souvent inutilisé, les librairies spéciales passées au client lors du démarrage
`/servers/MineCityLifeRP-1.7.10/servermeta.json` : Paramètres du serveur
`/meta/distrometa.json` : Paramètres du launcher

Une fois ces fichiers modifiés, envoyer les modifications :
1. `git add .` pour mettre les fichiers modifiés en attente de commit
2. `git commit -m "MESSAGE DE COMMIT"` pour commit les fichiers (écrire un message interressant pour l'historique, exemple : "Mise à jour de Mod (1.0 -> 2.0)")
3. `git push` pour envoyer le commit sur Github, il demandera vos identifiants et votre mot de passe pour Github

Dès que la modification est envoyée, une Action est lancée pour générer le nouveau distribution.json, il est possible d'en suivre le déroulement dans l'onglet "Actions" en haut de la page Github. (/!\ une coche verte ne signifie pas que l'Action à réussi, seulement qu'il n'y a pas eu d'erreurs rapportées (et Nebula ne rapporte pas d'erreur !) vérifier le job "Générer la distribution finale" est donc trés important.)

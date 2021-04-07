# Distribution
Fichiers nécessaires au fonctionnement du launcher

# Comment modifier ?
## Prérequis
Avoir [Git](https://git-scm.com/downloads) installé !\

## Ensuite ? Cloner le dépot
Choisir un emplacement et ouvrir un `cmd` à l'intérieur (sous Windows, cliquer sur la barre d'adresse en haut du navigateur de fichier et remplacer l'adresse par `cmd` puis taper Entrer). Normalement une fenêtre noire s'ouvre avec l'adresse du dossier choisi.\
\
Ensuite, il faut cloner ce dépôt : taper `git clone https://github.com/MineCityLife/Distribution` dans le `cmd` ouvert puis Entrer.\
\
Le dépôt se clone alors dans le dossier `Distribution` qui sera crée, utilisez `dir Distribution` pour vous rendre dans ce dossier.

## Avant toute modification !
Avant de commencer à modifier quoi que ce soit, vous devez vous assurer que la copie de ce dépôt sur votre PC est à jour, tapez `git pull` dans un `cmd` (attention à bien vous situer dans le dossier du dépôt qui s'appelle par défaut `Distribution`).\
\
Si vous savez que quelqu'un a modifié le dépot depuis que vous avez actualisé, actualisez à nouveau ! Le plus souvent c'est fait, le moins de problèmes peuvent arriver.

## Que modifier ?
Beaucoup de fichiers sont recompilés en un seul (le fichier `distribution.json` mais n'y touchez pas !) pour faire fonctionner le launcher. Ces fichiers/dossiers sont :

`/servers/.../forgemods/required` : Dossier contenant les mods requis pour jouer sur le serveur\
`/servers/.../forgemods/optionalon` : Les mods optionels qui peuvent être désactivés par le joueur mais qui sont par défaut activés\
`/servers/.../forgemods/optionaloff` : Les mods optionels qui peuvent être activés par le joueur mais qui sont par défaut désactivés\
`/servers/.../files/` : Les fichiers qui seront installés dans le dossier équivalent du .minecraft du joueur (par exemple les configurations de mods, etc.)\
`/servers/.../libraries/` : Souvent inutilisé, les librairies spéciales passées au client lors du démarrage\
`/servers/.../servermeta.json` : Paramètres du serveur\
`/meta/distrometa.json` : Paramètres du launcher\

## Et ensuite ?
Une fois ces fichiers modifiés, il faut sauvegarder puis envoyer les modifications, pour cela, trois commandes !
1. `git add .` pour mettre les fichiers modifiés dans la liste "En attente de commit"\
2. `git commit -m "[MESSAGE DE COMMIT]"` pour créer un commit (une modification) avec les fichiers dans la liste (pensez à écrire un message interressant car il est stocké dans l'historique, exemple : "Mise à jour de FurnituresMod (1.0 -> 2.0)")\
3. `git push` pour envoyer le commit juste crée sur Github, il demandera vos identifiants et votre mot de passe pour Github\

## Appliquer les changements
Une fois que vous avez envoyé les modifications des fichiers, un robot (une Action) reçoit l'ordre de créer le fichier `distribution.json` à partir des petits fichiers que vous avez modifiés.\
Il est **trés** recommandé de regarder le déroulement de l'Action et de vérifier qu'il n'y a pas de problèmes, normalement si une erreur survient le fichier `distribution.json` n'est pas modifié mais il peut arriver qu'il se casse, ou, même s'il n'est pas modifier, savoir d'où provient le problème est une bonne chose, non ?\

__**/!\ une coche verte ne signifie pas que l'Action à réussi, seulement qu'il n'y a pas eu d'erreurs rapportées (et Nebula ne rapporte pas d'erreur !) vérifier le job "Générer la distribution finale" est donc trés important.**__

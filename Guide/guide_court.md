# Windows 11
Un guide d'installation et d'optimisation complet et sans risques.

## Créer une clé USB d'installation
La première étape, c'est de créer une clé USB d'installation de Windows, qu'on pourra utiliser pour formater un PC et réinstaller Windows proprement.

Il faut pour ça **une clé USB de 8 Go ou plus** et **accès à un PC sous Windows**.

- Télécharger l'outil de la catégorie "Création d'un support d'installation de Windows 11" sur [le site de Microsoft.](https://www.microsoft.com/fr-fr/software-download/windows11)
- Lancer l'outil, choisir ses paramètres et sa clé, puis lancer le processus.

La clé va ensuite se créer toute seule. L'opération peut prendre du temps selon la connexion, la clé USB, et le PC.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20"> 1 - Créer une clé USB d'installation](https://youtu.be/nidskw_JslQ)

## Installer Windows

La clé étant créée, on va pouvoir l'utiliser pour formater le PC et installer une version fraîche de Windows.

Pour faire ça: 
- Mettre la clé dans un des ports à l'arrière du PC, directement sur la carte mère.
- Démarrer le PC, et spammer la touche **F11** pendant le démarrage.
- Choisir la clé USB dans le menu de démarrage qui s'ouvre (en UEFI si il y en a plusieurs).
- Se laisser guider par l'installateur de Windows.

**Attention ! Lors du choix du lecteur sur lequel installer Windows, il faut être très attentif, c'est ici que vous allez formater vos disques, en faisant pas attention vous allez formater des choses que vous vouliez garder !**

- Chaque SSD ou disque dur dans le PC correspond à un lecteur sur l'interface.
- Déterminer sur quel disque (lecteur) l'installation de Windows sera faite (on pourra s'aider de la taille pour les reconnaître).
- Supprimer toutes les partitions de ce que disque.
- Sélectionner l'espace non alloué représentant le disque, puis simplement appuyer sur suivant.

On pourra ensuite attendre la copie et l'installation de Windows. Pendant le compte à rebours de 10 secondes avant de redémarrer le PC, pensez à retirer la clé USB du PC. Ca évitera de redémarrer encore sur la clé et de recommencer l'installation en boucle.

Ensuite, on passe au réglage des paramètres initial avant de pouvoir accéder à Windows. On peut se laisser guider par l'installateur. Dites non à tout ce qu'il propose, et tout ira bien. Pour utiliser un compte local au lieu du compte Microsoft, on peut simplement entrer l'adresse mail "a" et le mot de passe "a". Après une erreur, on pourra continuer avec un compte local. Si vous choisissez d'utiliser un compte Microsoft (ce qui est très bien), faites attention de bien dire non à l'option pour sauvegarder vos dossiers sur OneDrive.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20"> 2 - Installer Windows](https://youtu.be/vSD2ZCxifDY)

## Installer ses pilotes

Une fois Windows installé et démarré, on va pouvoir télécharger et installer les pilotes. 

- On commence par se rendre sur le site de la carte mère, dans la catégorie support (si le modèle exacte de la carte mère est inconnu, on peut utiliser [UserDiag](https://userdiag.com/) pour le trouver). On télécharge ensuite tous les pilotes disponibles pour la carte mère.

- On fera quand même attention d'éviter les "utilitaires", qui ne sont pas vraiment des pilotes, mais plutôt des logiciels qui peuvent permettre de contrôler des choses diverses sur le PC, mais qui sont souvent mal faits et très gourmands en ressources.

- On passe également sur le site d'Nvidia ou AMD pour la carte graphique, et sur les sites des fabricants pour les pilotes divers spécifiques à du matériel particulier (logiciel de clavier, pilote de carte son, etc).

Une fois tous les pilotes téléchargés, on peut les extraire et les installer, un par un. Dans la majorité des cas on pourra se contenter de ne redémarrer qu'une seule fois à la fin, mais si on constate des erreurs étranges, redémarrer après chaque pilote peut aider.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20"> 3 - Installer ses pilotes](https://youtu.be/olOuIQA1HzY)

## Configurer les paramètres de Windows

Une fois les pilotes installés, on va pouvoir mettre à jour et régler les paramètres de Windows. Le principe est assez simple : 
- Commencer par mettre complètement à jour Windows. Faire une recherche des MàJ, les installer, redémarrer le PC, et refaire une recherche des MàJ.
- Faire un tour de tous les paramètres de Windows, catégorie par catégorie, et régler les paramètres selon ce qui semble pertinent. Attention tout de même, on peut avoir envie de décocher beaucoup de choses dans les permissions diverses (dans la catégorie Confidentialité) mais ça n'a aucun intérêt de le faire, et c'est même dangeureux.

Une fois les paramètres réglés, on va aller changer le mode de gestion d'alimentation, en choisissant le meilleur selon le processeur du PC. On chercher "alimentation", et on peut directement clique sur Changer le mode de gestion d'alimentation. On choisit : 
- CPU AMD Ryzen 3XXX : Le mode de gestion “Ryzen balanced” est le meilleur mode. (il s’installe quand vous installez les pilotes de chipset)
- CPU AMD Ryzen 5XXX : Le mode de gestion “Utilisation normale” est le meilleur mode (vous pouvez bouger le slider dans Paramètres -> Système -> Alimentation pour un léger gain).
- Cpu Intel 12XXX : Le mode de gestion "Performances élevées" est le meilleur mode.
- CPU Intel (tous les autres) : Le mode de gestion "Performances élevées" est le meilleur mode. Vous avez la possibilité d'essayer le mode "Performance ultimes", pour un gain à peu près inexistant. Pour installer ce mode, vous pouvez vous référer à [ce guide de Tenforums](https://www.tenforums.com/tutorials/107613-add-remove-ultimate-performance-power-plan-windows-10-a.html).

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20"> 4 - Les paramètres de Windows](https://youtu.be/CmdQOGJdFV0)

## Bibliothèques C++

Les bibliothèques C++ (traduction libre) sont nécessaires à beaucoup d'applications et de jeux pour fonctionner. Certains vont les installer automatiquement, d'autres vont juste vous faire des erreurs et ne rien faire. On va donc tout installer maintenant, pour être tranquille.

- On télécharge le pack de bibliothèques C++ sur [le site de TechPowerup](https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one/).
- On extrait l'archive téléchargée.
- On lance **install_all** **en tant qu'administrateur**.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20"> 5 - Bibliothèques C++](https://youtu.be/Ck-65Ku7ohg)

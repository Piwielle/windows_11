# Windows 11
Un guide d'installation et d'optimisation complet et sans risques.

## Créer une clé USB d'installation
La première étape, c'est de créer une clé USB d'installation de Windows, qu'on pourra utiliser pour formater un PC et réinstaller Windows proprement.

Il faut pour ça **une clé USB de 8 Go ou plus** et **accès à un PC sous Windows**.

- Télécharger l'outil de la catégorie "Création d'un support d'installation de Windows 11" sur [le site de Microsoft.](https://www.microsoft.com/fr-fr/software-download/windows11)
- Lancer l'outil, choisir ses paramètres et sa clé, puis lancer le processus.

La clé va ensuite se créer toute seule. L'opération peut prendre du temps selon la connexion, la clé USB, et le PC.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 1 - Créer une clé USB d'installation](https://youtu.be/nidskw_JslQ)

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

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 2 - Installer Windows](https://youtu.be/vSD2ZCxifDY)

## Installer ses pilotes

Une fois Windows installé et démarré, on va pouvoir télécharger et installer les pilotes. 

- On commence par se rendre sur le site de la carte mère, dans la catégorie support (si le modèle exacte de la carte mère est inconnu, on peut utiliser [UserDiag](https://userdiag.com/) pour le trouver). On télécharge ensuite tous les pilotes disponibles pour la carte mère.

- On fera quand même attention d'éviter les "utilitaires", qui ne sont pas vraiment des pilotes, mais plutôt des logiciels qui peuvent permettre de contrôler des choses diverses sur le PC, mais qui sont souvent mal faits et très gourmands en ressources.

- On passe également sur le site d'Nvidia ou AMD pour la carte graphique, et sur les sites des fabricants pour les pilotes divers spécifiques à du matériel particulier (logiciel de clavier, pilote de carte son, etc).

Une fois tous les pilotes téléchargés, on peut les extraire et les installer, un par un. Dans la majorité des cas on pourra se contenter de ne redémarrer qu'une seule fois à la fin, mais si on constate des erreurs étranges, redémarrer après chaque pilote peut aider.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 3 - Installer ses pilotes](https://youtu.be/olOuIQA1HzY)

## Configurer les paramètres de Windows

Une fois les pilotes installés, on va pouvoir mettre à jour et régler les paramètres de Windows. Le principe est assez simple : 
- Commencer par mettre complètement à jour Windows. Faire une recherche des MàJ, les installer, redémarrer le PC, et refaire une recherche des MàJ.
- Faire un tour de tous les paramètres de Windows, catégorie par catégorie, et régler les paramètres selon ce qui semble pertinent. Attention tout de même, on peut avoir envie de décocher beaucoup de choses dans les permissions diverses (dans la catégorie Confidentialité) mais ça n'a aucun intérêt de le faire, et c'est même dangeureux.

Une fois les paramètres réglés, on va aller changer le mode de gestion d'alimentation, en choisissant le meilleur selon le processeur du PC. On chercher "alimentation", et on peut directement clique sur Changer le mode de gestion d'alimentation. On choisit : 
- CPU AMD Ryzen 3XXX : Le mode de gestion “Ryzen balanced” est le meilleur mode. (il s’installe quand vous installez les pilotes de chipset)
- CPU AMD Ryzen 5XXX : Le mode de gestion “Utilisation normale” est le meilleur mode (vous pouvez bouger le slider dans Paramètres -> Système -> Alimentation pour un léger gain).
- Cpu Intel 12XXX : Le mode de gestion "Performances élevées" est le meilleur mode.
- CPU Intel (tous les autres) : Le mode de gestion "Performances élevées" est le meilleur mode. Vous avez la possibilité d'essayer le mode "Performance ultimes", pour un gain à peu près inexistant. Pour installer ce mode, vous pouvez vous référer à [ce guide de Tenforums](https://www.tenforums.com/tutorials/107613-add-remove-ultimate-performance-power-plan-windows-10-a.html).

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 4 - Les paramètres de Windows](https://youtu.be/CmdQOGJdFV0)

## Bibliothèques C++

Les bibliothèques C++ (traduction libre) sont nécessaires à beaucoup d'applications et de jeux pour fonctionner. Certains vont les installer automatiquement, d'autres vont juste vous faire des erreurs et ne rien faire. On va donc tout installer maintenant, pour être tranquille.

- On télécharge le pack de bibliothèques C++ sur [le site de TechPowerup](https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one/).
- On extrait l'archive téléchargée.
- On lance **install_all** **en tant qu'administrateur**.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 5 - Bibliothèques C++](https://youtu.be/Ck-65Ku7ohg)

## W10Privacy

W10Privacy est un "logiciel de vie privée". Généralement, c'est les logiciels qui sont déconseillés, parce que ça change des choses au hasard dans Windows, et c'est souvent n'importe quoi. Ceci dit, W10Privacy est un logiciel assez bien fait, donne des descriptions précises des options proposées, et permet de revenir en arrière assez facilement. On peut donc envisager de l'utiliser (mais c'est complètement facultatif).

- Télécharger le logiciel [sur le site officiel](https://www.w10privacy.de/deutsch-start/download/).
- L'installer, ou utiliser la version portable, selon les préférences (le choix est disponible pendant l'installation).
- Le lancer en tant qu'administrateur.
- **Créer une sauvegarde des paramètres actuels. Aller dans le menu "Configuration" -> Choisir "Enregistrer sous" -> Cliquer sur "Choisir le chemin" et sauvegarder la configuration dans un endroit sûr. Cliquer sur "Enregistrer" pour l'enregistrer. Il s'agit de la sauvegarde à utiliser en cas de problème, faites attention.**
- Lire et régler les paramètres de son choix, puis les appliquer et redémarrer le PC.

Si jamais vous ne voulez pas lire, je propose un [fichier de configuration à importer](https://lien.ctrl-f.io/w10privacy) qui est très basique, et qui devrait convenir à tout le monde. Dans tous les cas, **gardez bien votre sauvegarde**.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 6 - W10Privacy](https://youtu.be/2p92Mm-0YTo)

## Optimiser Windows

En plus des paramètres, on peut rajouter quelques optimisations pour Windows 11, pour réduire un peu les ressources utilisées par l'OS pour des choses  inutiles. C'est l'objet d'un autre guide dédié, [consultable ici](https://github.com/Piwielle/windows_11/blob/main/Optis/README.md).

Cette liste d'optimisations est sans risque pour le PC et ses fonctionnalités, mais le guide reste réversible et vous indique comment tout annuler si besoin.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 7 - Optimiser Windows](https://youtu.be/oejGj2dcjI8)

## Optimiser une CG Nvidia

Pour optimiser sa CG Nvidia, la première étape et d'utiliser [DDU](https://www.wagnardsoft.com/forums/viewforum.php?f=5) et [NVCleanInstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/) pour supprimer complètement son pilote graphique actuel, et le réinstaller en sélectionnant uniquement les morceaux du driver qu'on veut utiliser, plutôt que de tout installer.

- Télécharger [DDU](https://www.wagnardsoft.com/forums/viewforum.php?f=5), [NVCleanInstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/).
- Aller en mode sans échec, et utiliser DDU pour nettoyer le pilote graphique actuel. Désactiver aussi temporairement l'installation des pilotes par Windows Update, dans les paramètres de DDU.
- Redémarrer le PC, utiliser NVCleanInstall pour installer son pilote graphique. Choisir ce que vous voulez cocher pou non dans la liste, les options sont bien décrites.
- Relancer DDU, et réactiver l'installation des pilotes par Windows Update.

La seconde étape consiste à aller faire un tour de tous les paramètres du panneau Nvidia, puis cocher pour décocher ce qui vous semble pertinent, selon votre utilisation. Si vous ne savez pas trop quoi faire, la vidéo de ce chapitre a des suggestions.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 8 - Optimiser une CG Nvidia](https://youtu.be/kGRlhVB6YmE)

## Les bonnes pratiques

L'installation de Windows est terminée, mais avant de vous laisser, on va parler des bonnes pratiques et des choses à faire sur le PC pour essayer de le garder propre le plus longtemps possible, et éviter les problèmes.

- Eviter les optimisations. Malgré les promesses de gain de performances, d'input lag ou de stabilité, dans 99% des cas, il s'agit de bêtises qui vont vous flinguer Windows complètement, ou vous faire perdre des fonctionnalités pour ne rien gagner. Si ça vous amuse de bidouiller, et que ça vous dérange pas de réinstaller Windows tous les mois, vous pouvez tenter l'aventure, mais sauvegardez vos données, et soyez prêts à perdre du temps.
- Eviter les logiciels de nettoyage. Les Ccleaner, Iobit SystemCare, Glary utilities, DriversCloud, DriverBooster, etc etc, c'est des saloperies. Ils vendent du vent, et ne vont rien faire de bien sur votre PC. Pour nettoyer les fichiers, le nettoyage de disque intégré à Windows est efficace et moins dangeureux que ces outils.
- Garder son PC à jour. Ca inclut Windows, Defender, les applications, les jeux. N'allez pas forcément installer toutes les mises à jour de tout dès le premier jour, mais une fois qu'une mise à jour de quelque chose a une semaine, vous pouvez l'installer sans problèmes.
- Essayez d'installer le moins d'applications possible. Pour garder un PC propre, installer une application seulement si vous en avez vraiment besoin. Dans la mesure du possible, utilisez les versions portables des applications, qui peuvent laisser moins de bordel sur le PC.
- Eviter les cracks. Essayez d'utiliser des alternatives gratuites, c'est souvent possible, et bien moins dangeureux. Le site [AlternativeTo](https://alternativeto.net/) peut vous aider à trouver des alternative à un logiciel.
- Installez [uBlock Origin](https://ublockorigin.com/). Quel que soit votre navigateur, c'est essentiel d'avoir un bloqueur de pub efficace pour être tranquille sur internet. uBlock Origin est de loin le meilleur bloqueur de pub, et si vous en utilisez un autre, il est temps de le désinstaller et de changer.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 9 - Les bonnes pratiques](https://youtu.be/SEdYm2gLgYk)

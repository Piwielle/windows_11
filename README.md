# Windows 11

Windows 11, pour l'instant, c'est un peu pourri. Y'a des bugs qui réduisent les performances avec les CPU AMD, la barre des tâches est pas vraiment fonctionnelle, l'interface du menu démarrer non plus.

Mais bon, c'est l'avenir. Avec les nouvelles sorties de matériel (salut Alder Lake), et de logiciels/jeux, la meilleure expérience sera sur Windows 11, que ça me plaise ou non.

Je vais lister ici les tweaks que j'utilise pour rendre l'OS un peu plus agréable à utiliser, c'est un peu expérimental, et en cours d'évolution.

## Table des matières

 - [**1/ Le clic droit**](#1-le-clic-droit)
 - [**2/ Les tâches de fond**](#2-les-apps-en-tâche-de-fond)
 - [**3/ La GameBar**](#3-la-game-bar)
 - [**4/ Les animations**](#4-les-animations-de-windows)
 - [**5/ Le menu démarrer**](#5-le-menu-démarrer)

## 1/ Le clic droit.

Le clic droit de Windows 11 ressemble à ça : 

![image menu](https://i.imgur.com/l6MxFzI.png)

Alors oui, c'est très joli y'a des icônes. Mais si je veux utiliser 7zip pour extraire une archive, ou alors accéder à mon panneau nvidia, je suis obligé de cliquer sur "Afficher plus d'options", puis sur ce que je veux. C'est pénible.

On va donc remettre le clic droit de Windows 10, que je trouve plus efficace.

### 1.1/ Modification.

Pour récupérer le clic droit de Windows 10, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### 1.2/ Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de supprimer la clé de registre qu'on a modifié.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## 2/ Les apps en tâche de fond.

C'est un réglage qui était présent sur windows 10 :

![réglage windows 10](https://docs.microsoft.com/en-us/windows/application-management/images/backgroundapps-setting.png)

Sur Windows 11, il n'y a plus de réglage global. La seule possibilité est d'aller le désactiver individuemment pour chaque application, une par une. C'est très pénible, et je voudrais pouvoir tout désactiver d'un coup.

### 2.1/ Modification

Pour interdire aux applications de tourner en tâche de fond, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\AppPrivacy" /v LetAppsRunInBackground /t REG_DWORD /d 00000002 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### 2.2/ Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de supprimer la clé de registre qu'on a modifié.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg delete "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\AppPrivacy" /v LetAppsRunInBackground /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## 3/ La Game Bar.
Sur Windows 11, le réglage pour désactiver la Game Bar a disparu. La seule chose présente dans les paramètres, c'est une option pour ne pas l'ouvrir en appuyant sur un bouton de manette.

Elle se lance quand même systématiquement quand on lance un jeu. 
/!\ Certaines personnes utilisent la Game Bar, et trouvent ça utile. Si c'est votre cas, n'appliquez évidemment pas ces modifications, qui vont la désactiver.

### 3.1/ Modification.

Pour désactiver la Game Bar, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Coller la ligne :

```reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### 3.2/ Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne 

```reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000001 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Coller la ligne 

```reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000001 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## 4/ Les animations de Windows

Y'a plein d'animations dans Windows 11. Pour le menu démarrer, le scroll, l'ouverture/fermeture des fenêtres. Je les trouve lentes, et je préfère les désactiver.

![animation](https://i.imgur.com/QqcfhrJ.gif)

### 4.1/ Modification.

Pour une fois, il s'agit d'un simple paramètre de Windows à changer.
- Paramètres
- -> Accessibilité
- -> Effets Visuels
- Décocher ```Effets d'animation```

### 4.2/ Annuler le changement.

Pour une fois, il s'agit d'un simple paramètre de Windows à changer.
- Paramètres
- -> Accessibilité
- -> Effets Visuels
- Cocher ```Effets d'animation```

## 5/ le menu démarrer

Le menu démarrer de Windows 11 est médiocre, et pas fonctionnel. Je suis limité à 18 raccourcis affichés maximum (à moins d'utiliser les pages, et de devoir scroll, avec leur scroll pas réactif), on est forcé d'afficher les objets "recommandés" (on peut les cacher, mais dans ce cas on se retrouve avec un cadre vide qui nous dit de les activer...)

![start menu](https://i.imgur.com/XCvE4fq.png)

Quel enfer. J'ai pas encore trouvé de solution viable.

edit : en train de tester https://www.startallback.com/

edit 2 : startallback = nul (uniquement vertical, pas possible de faire des groupes de raccourcis sur plusieurs colonnes)
du coup je test https://www.stardock.com/products/start11/

edit 3 : start11 c'est pas parfait non plus (le scroll est pas fluide, on peut pas définir de transparance pour le fond des icones pinned), mais c'est mieux que startallback, et c'est en développement actif, j'ai donné du feedback on verra bien. Sinon, j'ai essayé de couper des services au hasard pour voir, j'ai éclaté mon install, et j'ai dû tout réactiver depuis winRE, c'était pas ouf. Faites attention. Je teste aussi le logiciel https://github.com/builtbybel/ThisIsWin11.

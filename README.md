# Windows 11

Windows 11, pour l'instant, c'est un peu pourri. Y'a des bugs qui réduisent les performances avec les CPU AMD, la barre des tâches est pas vraiment fonctionnelle, l'interface du menu démarrer non plus.

Mais bon, c'est l'avenir. Avec les nouvelles sorties de matériel (Alder Lake), et de logiciels/jeux, la meilleure expérience sera sur Windows 11, que ça me plaise ou non.

Je vais lister ici les tweaks que j'utilise pour rendre l'OS un peu plus agréable à utiliser, c'est un peu expérimental, et en cours d'évolution.

## Table des matières

 - [**1/ Le clic droit**](#1-le-clic-droit)
 - [**2/ Les tâches de fond**](#2-les-apps-en-tâche-de-fond)
 - [**3/ La GameBar**](#3-la-game-bar)
 - [**4/ Les animations**](#4-les-animations-de-windows)
 - [**5/ La recommendation de Bing dans Microsoft Edge**](#5-la-recommendation-de-bing-dans-microsoft-edge)
 - [**6/ Le menu démarrer**](#6-le-menu-démarrer)
 - [**7/ Les résultats web dans la recherche**](#7-les-résultats-web-dans-la-recherche)
 - [**8/ Les widgets**](#8-les-widgets)

## Chapitre 0 : Liste des fonctionnalités perdues avec Windows 11

Avant de commencer, listons joyeuseuement ce qui ne fonctionne pas ou plus avec Windows 11 : 
- (liste non faite parce que l'auteur est un branleur)

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

## 5/ La recommendation de Bing dans Microsoft Edge
C'est ce truc là, qui apparaît au moins une fois par semaine. ![bing](https://i.imgur.com/4ywSfS2.png)

Pour le désactiver : 
- Aller sur l'url [`edge://flags/#edge-show-feature-recommendations`](edge://flags/#edge-show-feature-recommendations)
- Changer le réglage pour "Désactivé"
- Redémarrer Edge.

## 6/ le menu démarrer

Le menu démarrer de Windows 11 est médiocre, et pas fonctionnel. Je suis limité à 18 raccourcis affichés maximum (à moins d'utiliser les pages, et de devoir scroll, avec leur scroll pas réactif), on est forcé d'afficher les objets "recommandés" (on peut les cacher, mais dans ce cas on se retrouve avec un cadre vide qui nous dit de les activer...)

![start menu](https://i.imgur.com/XCvE4fq.png)

Quel enfer.

La meilleure solution que j'ai trouvé pour le moment, c'est d'acheter et d'utiliser start11. https://www.stardock.com/products/start11/

Mon menu démarrer actuel ressemble à ça 

![start menu](https://i.imgur.com/9iqa8nd.png)

C'est mieux, mais c'est payant (6€). Apparemment, une future mise à jour de windows 11 devrait améliorer le menu démarrer, et rajouter une ligne supplémentaire de raccourcis. C'est mieux, mais pas assez à mon goût, et la barre de "recommendations" reste impossible à cacher complètement.

## 7/ Les résultats web dans la recherche
Par défaut, Windows affiche des résultats du web dans la recherche du menu démarrer. 

![recherche](https://i.imgur.com/wnChamT.png)

C'est pénible, je veux le désactiver.

### 7.1/ Modification.

Pour désactiver la Game Bar, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000001 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### 7.2/ Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne 

```reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## 8/ Les widgets

Windows a ajouté une fonctionnalité, les widgets.
![widgets](https://img.bfmtv.com/c/0/708/dd3/9c94d037cdb46d167b8f1ff98fe49.png)

On peut assez simplement les désactiver dans les paramètres, mais le fait de simplement les désactiver ne suffit pas, et ils tournent toujours en tâche de fond même désactivés. Je souhaite donc vraiment les désactiver, et que plus rien ne tourne.

### 8.1/ Modification.

Pour désactiver les Widgets, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### 8.2/ Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne 

```reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

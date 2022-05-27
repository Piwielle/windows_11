# Windows 11

Windows 11, pour l'instant, c'est un peu pourri. Y'a des bugs qui réduisent les performances avec les CPU AMD, la barre des tâches est pas vraiment fonctionnelle, l'interface du menu démarrer non plus.

Mais bon, c'est l'avenir. Avec les nouvelles sorties de matériel (Alder Lake), et de logiciels/jeux, la meilleure expérience sera sur Windows 11, que ça me plaise ou non.

Je vais lister ici les tweaks que j'utilise pour rendre l'OS un peu plus agréable à utiliser, c'est un peu expérimental, et en cours d'évolution.

## Table des matières

 - [**Le clic droit**](#le-clic-droit)
 - [**La Game Bar**](#la-game-bar)
 - [**Les animations**](#les-animations-de-windows)
 - [**Microsoft Edge**](#microsoft-edge)
 - [**Le menu démarrer**](#le-menu-démarrer)
 - [**Les résultats web dans la recherche**](#les-résultats-web-dans-la-recherche)
 - [**Les widgets**](#les-widgets)
 - [**TLDR (tout d'un coup)**](#tldr-tout-dun-coup)

## Chapitre 0 : Liste des fonctionnalités perdues avec Windows 11

Avant de commencer, listons joyeuseuement ce qui ne fonctionne pas ou plus avec Windows 11 : 
- (liste non faite parce que l'auteur est un branleur)

## Le clic droit.

Le clic droit de Windows 11 ressemble à ça : 

![image menu](https://i.imgur.com/l6MxFzI.png)

Alors oui, c'est très joli y'a des icônes. Mais si je veux utiliser 7zip pour extraire une archive, ou alors accéder à mon panneau nvidia, je suis obligé de cliquer sur "Afficher plus d'options", puis sur ce que je veux. C'est pénible.

On va donc remettre le clic droit de Windows 10, que je trouve plus efficace.

### Modification.

Pour récupérer le clic droit de Windows 10, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de supprimer la clé de registre qu'on a modifié.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.


## La Game Bar.
Sur Windows 11, le réglage pour désactiver la Game Bar a disparu. La seule chose présente dans les paramètres, c'est une option pour ne pas l'ouvrir en appuyant sur un bouton de manette.

Elle se lance quand même systématiquement quand on lance un jeu. 

/!\ Certaines personnes utilisent la Game Bar, et trouvent ça utile. Si c'est votre cas, n'appliquez évidemment pas ces modifications, qui vont la désactiver.

### Modification.

Pour désactiver la Game Bar, il faut modifier deux clés de registre, ce qu'on peut faire via le Terminal, et désinstaller une application.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```Get-AppxPackage Microsoft.XboxGamingOverlay | Remove-AppxPackage```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Coller la ligne :

```reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Coller la ligne :

```reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs, et réinstaller l'application.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```Get-AppxPackage -allusers *Microsoft.XboxGamingOverlay* | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register “$($_.InstallLocation)\AppXManifest.xml”}```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Coller la ligne 

```reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000001 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Coller la ligne 

```reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000001 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## Les animations de Windows

Y'a plein d'animations dans Windows 11. Pour le menu démarrer, le scroll, l'ouverture/fermeture des fenêtres. Je les trouve lentes, et je préfère les désactiver.

![animation](https://i.imgur.com/QqcfhrJ.gif)

### Modification.

Pour une fois, il s'agit d'un simple paramètre de Windows à changer.
- Paramètres
- -> Accessibilité
- -> Effets Visuels
- Décocher ```Effets d'animation```

### Annuler le changement.

Pour une fois, il s'agit d'un simple paramètre de Windows à changer.
- Paramètres
- -> Accessibilité
- -> Effets Visuels
- Cocher ```Effets d'animation```

## Microsoft Edge
Deux choses. Par défaut, Edge se lance automatiquement au démarrage du PC, et reste en tâche de fond même si le logiciel n'est pas démarré. On peut désactiver ça dans les options.

Il y a aussi la pub pour Bing.
C'est ce truc là, qui apparaît au moins une fois par semaine.

<img src="https://i.imgur.com/4ywSfS2.png" width="300" height="400">


Pour désactiver ces deux choses : 
- Aller sur l'url (depuis Edge) [`edge://settings/system`](edge://settings/system)
- Désactiver les options **"démarrage rapide"** et **"Continuer à exécuter les extensions et les applications en arrière plan lorsque Microsft Edge est fermé"**.


- Aller sur l'url [`edge://flags/#edge-show-feature-recommendations`](edge://flags/#edge-show-feature-recommendations)
- Changer le réglage pour "Désactivé"
- Redémarrer Edge.

## 5/ Le menu démarrer

Le menu démarrer de Windows 11 est médiocre, et pas fonctionnel. Je suis limité à 18 raccourcis affichés maximum (à moins d'utiliser les pages, et de devoir scroll, avec leur scroll pas réactif), on est forcé d'afficher les objets "recommandés" (on peut les cacher, mais dans ce cas on se retrouve avec un cadre vide qui nous dit de les activer...)

![start menu](https://i.imgur.com/XCvE4fq.png)

Quel enfer.

J'ai essayé Start11 (trop lent), et StartAllBack (pas de possibilités de mettre plusieurs colonnes et groupes), et rien m'a convaincu.

La meilleure option que je suggère c'est https://github.com/valinet/ExplorerPatcher. Ca remet le menu de Windows 10, c'est rapide, et assez configrable.
Mon menu démarrer actuel ressemble à ça avec ExplorerPatcher : 

![explorer patcher](https://i.imgur.com/XM5RZWk.png)

## Les résultats web dans la recherche
Par défaut, Windows affiche des résultats du web dans la recherche du menu démarrer. 

![recherche](https://i.imgur.com/wnChamT.png)

C'est pénible, je veux le désactiver.

### Modification.

Pour désactiver les résultats web dans la recherche, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000001 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne 

```reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## Les widgets

Windows a ajouté une fonctionnalité, les widgets.
![widgets](https://img.bfmtv.com/c/0/708/dd3/9c94d037cdb46d167b8f1ff98fe49.png)

On peut assez simplement les désactiver dans les paramètres, mais le fait de simplement les désactiver ne suffit pas, et ils tournent toujours en tâche de fond même désactivés. Je souhaite donc vraiment les désactiver, et que plus rien ne tourne.

### Modification.

Pour désactiver les Widgets, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne 

```reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## TLDR (tout d'un coup)

Je mets ici directement la liste de toutes les commandes de ce doc, pour avoir tout d'un coup sans devoir tout lire.
Pour désactiver : 
```
Get-AppxPackage Microsoft.XboxGamingOverlay | Remove-AppxPackage
reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000001 /f
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Control Panel\Desktop\WindowMetrics" /v MinAnimate /t REG_SZ /d 00000000 /f
```

Et pour réactiver : 
```
Get-AppxPackage -allusers *Microsoft.XboxGamingOverlay* | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register “$($_.InstallLocation)\AppXManifest.xml”}
reg delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f
reg delete "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\AppPrivacy" /v LetAppsRunInBackground /f
reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /f
reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Control Panel\Desktop\WindowMetrics" /v MinAnimate /t REG_SZ /d 00000000 /f
```

A noter que certaines parties (le menu démarrer, les recommendations de bing) ne sont pas modifiées via le registre, et ne sont du coup pas modifiées par les commandes au dessus !

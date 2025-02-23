# Windows 11

Windows 11 c'est l'avenir. Avec les nouvelles sorties de matériel (exemple Alder Lake), et de logiciels/jeux, la meilleure expérience sera sur cette version, que ça me plaise ou non.

Alors voilà la liste des tweaks que je suggère pour Windows 11. Pour chaque modification, il y a une explication brève de ce que ça fait.

Pour annuler n'importe laquelle de ces modifications, la procédure est décrite [dans ce guide séparé](https://github.com/Piwielle/windows_11/blob/main/Optis/Annuler.md).

## Liste des tweaks

 - [**Le clic droit**](#le-clic-droit)
 - [**La Game Bar**](#la-game-bar)
 - [**Microsoft Edge**](#microsoft-edge)
 - [**Le menu démarrer**](#le-menu-démarrer)
 - [**Les résultats web dans la recherche**](#les-résultats-web-dans-la-recherche)
 - [**Les widgets**](#les-widgets)
 - [**L'hibernation**](#lhibernation)
 - [**Service SysMain**](#service-sysmain)
 - [**VBS**](#vbs)
 - [**Windows Copilot**](#windows-copilot)
 - [**Brave**](#brave)
 - [**TLDR (tout d'un coup)**](#tldr-tout-dun-coup)

## Le clic droit

Le clic droit de Windows 11 ressemble à ça : 

<img src="https://i.imgur.com/l6MxFzI.png" width="280" height="330" alt="qsddsq" class="sdfdfs">

Alors oui, c'est très joli y'a des icônes. Mais si je veux utiliser 7zip pour extraire une archive, ou alors accéder à mon panneau nvidia, je suis obligé de cliquer sur "Afficher plus d'options", puis sur ce que je veux. C'est pénible.
On va donc remettre le clic droit de Windows 10.


Pour récupérer le clic droit de Windows 10, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30" alt="vdszevz" class="fezfsd">
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## La Game Bar
La game bar est un overlay qui permet de régler des paramètres et d'afficher des choses par dessus son jeu. C'est quelque chose d'assez efficace, que je recommande de laisser. Voir [cette vidéo pour plus de détails](https://www.youtube.com/watch?v=ATPLXIPtDMg).

Ceci dit, la fonctionnalité d'enregistrement permanent des jeux de cette Game Bar impacte les performances du PC. Heureusement, on peut la désactiver.

Pour désactiver cette option, il faut modifier deux clés de registre, ce qu'on peut faire via le Terminal, et désinstaller une application.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller les lignes une par une :

```reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000000 /f```


```reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000000 /f```
- Vérifier que les réponses confirment que les opérations ont bien été effectuées.
- Redémarrer le PC.

## Microsoft Edge
Plusieurs choses. Par défaut, Edge se lance automatiquement au démarrage du PC, et reste en tâche de fond même si le logiciel n'est pas démarré. On peut désactiver ça dans les options.

Il y a aussi la pub pour Bing.
C'est ce truc là, qui apparaît au moins une fois par semaine.

<img src="https://i.imgur.com/4ywSfS2.png" width="300" height="400" alt="zefsqq" class="dddsqdqsd">

Et récemment, Microsoft a eu la joyeuse idée de rajouter un gros bouton Bing qui s'ouvre dès qu'on passe la souris dessus, sans cliquer. Quelle horreur.

<img src="https://i.imgur.com/G40UvD5.png" width="162" height="126" alt="vxcvsdfd" class="qsdzadadad">

Et maintenant, Edge se met à suggérer régulièrement de changer de moteur de recherche pour passer à Bing (mdr).

Pour désactiver ça : 
- Aller sur l'url (depuis Edge) [`edge://settings/system`](edge://settings/system)
- Désactiver les options **"démarrage rapide"** et **"Continuer à exécuter les extensions et les applications en arrière plan lorsque Microsoft Edge est fermé"**.

  
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller les lignes une par une :

```reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v HubsSidebarEnabled /t REG_DWORD /d 00000000 /f```


```reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v ShowRecommendationsEnabled /t REG_DWORD /d 00000000 /f```


```reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v SpotlightExperiencesAndRecommendationsEnabled /t REG_DWORD /d 00000000 /f```

```reg add HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge /v DefaultBrowserSettingEnabled /t REG_DWORD /d 00000000 /f```

- Vérifier que les réponses confirment que les opérations ont bien été effectuées.
- Redémarrer le navigateur.

/!\ En faisant ça, on modifie des stratégies de groupe, c'est une manière de faire qui est plutôt destinée aux entreprises, mais c'est celle qui fonctionne le mieux. Pour signaler qu'on a fait ça, Edge va afficher un bandeau dans les paramètres qui dit que le navigateur est géré par une organisation.

<img src="https://i.imgur.com/lwkhX9E.png" width="337" height="45" alt="cxwqscqs" class="qsdqszadza">

C'est normal, et c'est uniquement les modifications qu'on a fait, le navigateur n'est pas réellement géré par une organisation. Pour supprimer ce message, il faut inverser les modifications qu'on a fait, et il disparaîtra.


## Le menu démarrer

Le menu démarrer de Windows 11 est médiocre, et pas fonctionnel. Je suis limité à 18 raccourcis affichés maximum (à moins d'utiliser les pages, et de devoir scroll, avec leur scroll pas réactif), on est forcé d'afficher les objets "recommandés" (on peut les cacher, mais dans ce cas on se retrouve avec un cadre vide qui nous dit de les activer...)

<img src="https://i.imgur.com/XCvE4fq.png" width="660" height="730">

Quel enfer.

J'ai essayé Start11 (trop lent), et StartAllBack (pas de possibilités de mettre plusieurs colonnes et groupes), et rien m'a convaincu.

La meilleure option que je suggère c'est https://github.com/valinet/ExplorerPatcher. Ca remet le menu de Windows 10, c'est rapide, et assez configurable.
Mon menu démarrer actuel ressemble à ça avec ExplorerPatcher : 

<img src="https://i.imgur.com/XM5RZWk.png" width="1010" height="600">

## Les résultats web dans la recherche
Par défaut, Windows affiche des résultats du web dans la recherche du menu démarrer. 

<img src="https://i.imgur.com/wnChamT.png" width="790" height="740">

C'est pénible, je veux le désactiver.

Pour désactiver les résultats web dans la recherche, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000001 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## Les widgets

Windows a ajouté une fonctionnalité, les widgets.

<img src="https://i.imgur.com/auGcKRH.png" width="570" height="670">

On peut assez simplement les désactiver dans les paramètres, mais le fait de simplement les désactiver ne suffit pas, et ils tournent toujours en tâche de fond même désactivés. Je souhaite donc vraiment les désactiver, et que plus rien ne tourne.

Pour désactiver les Widgets, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller la ligne :

```reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## L'hibernation
Par défaut, Windows se met en veille prolongée au lieu de vraiment s'éteindre quand on l'éteint. Ca permet d'accélérer un peu le démarrage, mais ça peut causer plein de soucis divers et variés parce que Windows s'éteint jamais vraiment. Je suggère de désactiver cette fonctionnalité, quitte à avoir un PC qui démarre un peu moins vite.

Pour désactiver l'hibernation, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller les lignes :

```REG ADD "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Power" /v HiberbootEnabled /t REG_DWORD /d 00000000 /f```


```powercfg -h off```
- Vérifier que les réponses confirment que les opérations ont bien été effectué.
- Redémarrer le PC.

## Service SysMain
C'est un service qui analyse l'utilisation du PC, et qui pré charge des applications dans la RAM, pour permettre de les lancer plus rapidement. Fonctionne souvent bien, mais peut créer des soucis d'utilisation de disque dur, pour un gain qui n'est pas forcément utile.

Pour désactiver le service, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Cliquer sur la petite flèche dans la barre du haut, puis ouvrir un **Invite de commande**
- Coller la ligne :

```sc stop "SysMain" & sc config "SysMain" start=disabled```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## VBS

La VBS (Virtualization Based Security) est une option de sécurité de Windows. Elle permet d'augmenter un peu la sécurité, au prix d'une réduction de performances. Désactiver cette option est un compromis, mais permet de gagner des performances en jeu pour une réduction minime de sécurité. Personnellement, je le fais. A chacun de décider selon ses préférences.

Pour désactiver l'option, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- CLiquer sur la petite flèche dans la barre du haut, puis ouvrir un **Invite de commande**
- Coller la ligne :

```reg add "HKLM\System\CurrentControlSet\Control\DeviceGuard\Scenarios\HypervisorEnforcedCodeIntegrity" /v Enabled /t REG_DWORD /d 0 /f```

```reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\DeviceGuard" /v EnableVirtualizationBasedSecurity /t REG_DWORD /d 0 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## Windows Copilot
Le nouvel assistant "AI" de Windows. Il n'est pas désactivable via les paramètres pour le moment, on peut uniquement cacher son icône.

Pour désactiver l'option, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- CLiquer sur la petite flèche dans la barre du haut, puis ouvrir un **Invite de commande**
- Coller la ligne :

```reg add "HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\WindowsCopilot" /v TurnOffWindowsCopilot /t REG_DWORD /d 1 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.


## Brave
Google a décidé de désactiver uBlock Origin (entre autres). Une des solutions pour pouvoir l'utiliser et d'utiliser un autre navigateur qui propose encore l'extension, comme Brave. Mais Brave a aussi son lot de saloperies, des options de crypto, d'intelligence artificielle et autres truics qui ne m'intéressent pas.
On peut complètement désactiver ces options.

Pour désactiver ces options, il faut modifier des clés de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- CLiquer sur la petite flèche dans la barre du haut, puis ouvrir un **Invite de commande**
- Coller la ligne :

```
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v BraveRewardsDisabled /t REG_DWORD /d 1 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v BraveWalletDisabled /t REG_DWORD /d 1 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v BraveVPNDisabled /t REG_DWORD /d 1 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v BraveAIChatEnabled /t REG_DWORD /d 0 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v PasswordManagerEnabled /t REG_DWORD /d 0 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v TorDisabled /t REG_DWORD /d 0 /f
pause
```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.


## TLDR (tout d'un coup)

Je mets ici directement la liste de toutes les commandes de ce doc, pour avoir tout d'un coup sans devoir tout lire. A utiliser uniquement si vous avez lu, et que vous savez ce que fait chaque modification, sinon vous risquez des mauvaises surprises.

```
reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000001 /f
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Control Panel\Desktop\WindowMetrics" /v MinAnimate /t REG_SZ /d 00000000 /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Power" /v HiberbootEnabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v HubsSidebarEnabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v ShowRecommendationsEnabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v SpotlightExperiencesAndRecommendationsEnabled /t REG_DWORD /d 00000000 /f
reg add HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge /v DefaultBrowserSettingEnabled /t REG_DWORD /d 00000000 /f
reg add "HKLM\System\CurrentControlSet\Control\DeviceGuard\Scenarios\HypervisorEnforcedCodeIntegrity" /v Enabled /t REG_DWORD /d 0 /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\DeviceGuard" /v EnableVirtualizationBasedSecurity /t REG_DWORD /d 0 /f
reg add "HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\WindowsCopilot" /v TurnOffWindowsCopilot /t REG_DWORD /d 1 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v BraveRewardsDisabled /t REG_DWORD /d 1 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v BraveWalletDisabled /t REG_DWORD /d 1 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v BraveVPNDisabled /t REG_DWORD /d 1 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v BraveAIChatEnabled /t REG_DWORD /d 0 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v PasswordManagerEnabled /t REG_DWORD /d 0 /f
reg add "HKEY_LOCAL_MACHINE\Software\Policies\BraveSoftware\Brave" /v TorDisabled /t REG_DWORD /d 0 /f
powercfg -h off
sc.exe stop "SysMain"
sc.exe config "SysMain" start=disabled
pause
```

A noter que certaines parties (le menu démarrer par exemple) ne sont pas modifiées via le registre, et ne sont du coup pas modifiées par les commandes au dessus !


# Windows 11

Ici la liste des commandes et isntructions pour inverser simplement tout ce qu'on a pu faire comme "optimisations".

## Annuler les tweaks

 - [**Inverser le clic droit**](#inverser-le-clic-droit)
 - [**Inverser la Game Bar**](#inverser-la-game-bar)
 - [**Inverser Microsoft Edge**](#inverser-microsoft-edge)
 - [**Inverser le menu démarrer**](#inverser-le-menu-démarrer)
 - [**Inverser les résultats web dans la recherche**](#inverser-les-résultats-web-dans-la-recherche)
 - [**Inverser les widgets**](#inverser-les-widgets)
 - [**Inverser l'hibernation**](#inverser-lhibernation)
 - [**Inverser service SysMain**](#inverser-service-sysmain)
 - [**Inverser TLDR (tout d'un coup)**](#inverser-tldr-tout-dun-coup)



## Inverser le clic droit

Pour annuler cette modification, il suffira de faire l'inverse et de supprimer la clé de registre qu'on a modifié.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller la ligne :

```reg delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.


## Inverser la Game Bar


Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller les lignes une par une :

```reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000001 /f```


```reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000001 /f```
- Vérifier que les réponses confirment que les opérations ont bien été effectuées.
- Redémarrer le PC.


## Inverser Microsoft Edge

- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller les lignes une par une :

```reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v HubsSidebarEnabled /f```

```reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v ShowRecommendationsEnabled /f```

- Vérifier que les réponses confirment que les opérations ont bien été effectuées.
- Redémarrer le navigateur.


## Inverser le menu démarrer

Il suffit de désinstaller ExplorerPatcher, et le menu démarrer de Windows 11 reviendra tout seul.

## Inverser les résultats web dans la recherche

Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller la ligne 

```reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000000 /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## Inverser les widgets
Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller la ligne 

```reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## Inverser l'hibernation

Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller les lignes :

```REG ADD "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Power" /v HiberbootEnabled /t REG_DWORD /d 00000001 /f```


```powercfg -h on```
- Vérifier que les réponses confirment que les opérations ont bien été effectuées.
- Redémarrer le PC.

## Inverser service SysMain

Pour annuler cette modification, il suffira de faire l'inverse et de changer les valeurs.
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Coller la ligne :

```sc config "SysMain" start=auto```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.


## Inverser TLDR (tout d'un coup)

Pour réactiver d'un coup tout ce qu'on a désactivé :
```
reg delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f
reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Dsh" /v AllowNewsAndInterests /f
reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v AppCaptureEnabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\System\GameConfigStore" /v GameDVR_Enabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Control Panel\Desktop\WindowMetrics" /v MinAnimate /t REG_SZ /d 00000000 /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Power" /v HiberbootEnabled /t REG_DWORD /d 00000001 /f
reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v HubsSidebarEnabled /f
reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge" /v ShowRecommendationsEnabled /f
powercfg -h on
sc config "SysMain" start=auto
```

A noter que certaines parties (le menu démarrer par exemple) ne sont pas modifiées via le registre, et ne sont du coup pas modifiées par les commandes au dessus !



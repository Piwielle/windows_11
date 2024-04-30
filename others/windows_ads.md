# Désactiver les publicités intégrés à Windows 11

Y'a des publicités qui sont intégrées dans Windows 11. C'est pénible. On va voir comment les désactiver. Ce tutoriel est tiré en grande partie d'un [article sur elevenforums](https://www.elevenforum.com/t/disable-ads-in-windows-11.8004/), j'ai simplement traduit des trucs, changé la méthode d'application, rajouté quelques images pour qu'on sache de quoi on parle et condensé le tout. Si tu parles anglais, tu peux aussi consulter l'article original.

## Bandeau de pub de l'explorateur de fichiers

<details>
  <summary>Exemple de ce que c'est (cliquer pour déplier)</summary> 
  
![bandeau pub](https://i.imgur.com/dbeI18r.png)
</details>

Pour désactiver ces publicités : 
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30" alt="vdszevz" class="fezfsd">
- Windows Terminal (Admin)
- Coller la ligne :

> **reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v ShowSyncProviderNotifications /t REG_DWORD /d 00000000 /f**
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.


## Publicités de l'écran de verrouillage

<details>
  <summary>Exemple de ce que c'est (cliquer pour déplier)</summary> 
  
![lockscreen](https://i.imgur.com/vc9SUos.png)
</details>

Pour désactiver ces publicités : 
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30" alt="vdszevz" class="fezfsd">
- Windows Terminal (Admin)
- Coller les lignes :

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v RotatingLockScreenOverlayEnabled /t REG_DWORD /d 00000000 /f**

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-338387Enabled /t REG_DWORD /d 00000000 /f**
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.



## Publicités dans les paramètres

<details>
  <summary>Exemple de ce que c'est (j'ai pas d'exemple mdr, c vide)</summary> 
  
</details>

Pour désactiver ces publicités : 
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30" alt="vdszevz" class="fezfsd">
- Windows Terminal (Admin)
- Coller les lignes :

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-338393Enabled /t REG_DWORD /d 00000000 /f**

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-353694Enabled /t REG_DWORD /d 00000000 /f**

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-353696Enabled /t REG_DWORD /d 00000000 /f**
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.


## Publicités dans les notifications

<details>
  <summary>Exemple de ce que c'est (cliquer pour déplier)</summary> 
  
  ![lockscreen](https://i.imgur.com/7SYPURr.png)
</details>

Pour désactiver ces publicités : 
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30" alt="vdszevz" class="fezfsd">
- Windows Terminal (Admin)
- Coller les lignes :

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-338393Enabled /t REG_DWORD /d 00000000 /f**

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-353694Enabled /t REG_DWORD /d 00000000 /f**

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-353696Enabled /t REG_DWORD /d 00000000 /f**
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.


## Publicités au démarrage

<details>
  <summary>Exemple de ce que c'est (cliquer pour déplier)</summary> 
  
  ![lockscreen](https://i.imgur.com/fEYowk0.png)
</details>

Pour désactiver ces publicités : 
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30" alt="vdszevz" class="fezfsd">
- Windows Terminal (Admin)
- Coller les lignes :

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\UserProfileEngagement" /v ScoobeSystemSettingEnabled /t REG_DWORD /d 00000000 /f**

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-310093Enabled /t REG_DWORD /d 00000000 /f**

- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.



## Publicités personnalisées

Ici c'est pas vraiment un affichage de publicités, c'est ce qui autorise Microsoft à récupérer des données sur toi pour te proposer des pubs plus adaptées à toi. Ca peut se désactiver aussi, mais ça ne réduira pas la quantité de pubs que tu vois.
La seconde ligne permet de réduire un petit peu les suggestions personnalisées.

Pour désactiver cette option : 
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30" alt="vdszevz" class="fezfsd">
- Windows Terminal (Admin)
- Coller les lignes :

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\AdvertisingInfo" /v Enabled /t REG_DWORD /d 00000000 /f**

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Privacy" /v TailoredExperiencesWithDiagnosticDataEnabled /t REG_DWORD /d 00000000 /f**

- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.


## Publicités du menu démarrer

<details>
  <summary>Exemple de ce que c'est (cliquer pour déplier)</summary> 
  
  ![lockscreen](https://i.imgur.com/5qN1Kkh.png)
</details>

Pour désactiver ces publicités : 
- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30" alt="vdszevz" class="fezfsd">
- Windows Terminal (Admin)
- Coller les lignes :

> **reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v Start_IrisRecommendations /t REG_DWORD /d 00000000 /f**

- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

## TL;DR (désactiver)

Pour tout désactiver d'un coup. Assure toi quand même de lire ce que chaque truc fait. Pour réactiver des trucs, c'est juste en dessous.
```
reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v ShowSyncProviderNotifications /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v RotatingLockScreenOverlayEnabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-338387Enabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-338393Enabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-353694Enabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-353696Enabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\UserProfileEngagement" /v ScoobeSystemSettingEnabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-310093Enabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\AdvertisingInfo" /v Enabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Privacy" /v TailoredExperiencesWithDiagnosticDataEnabled /t REG_DWORD /d 00000000 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v Start_IrisRecommendations /t REG_DWORD /d 00000000 /f
```

## TL;DR (réactiver)

Si tu veux réactiver les pubs parce que tu adores ça, ou bien que quelque chose marche plus sur ton PC et que tu penses que ça peut venir de ça, tu peux utiliser ça pour tout remettre par défaut.

```
reg add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v ShowSyncProviderNotifications /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v RotatingLockScreenOverlayEnabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-338387Enabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-338393Enabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-353694Enabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-353696Enabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\UserProfileEngagement" /v ScoobeSystemSettingEnabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v SubscribedContent-310093Enabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\AdvertisingInfo" /v Enabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Privacy" /v TailoredExperiencesWithDiagnosticDataEnabled /t REG_DWORD /d 00000001 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v Start_IrisRecommendations /t REG_DWORD /d 00000001 /f
```

[<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb">Y'a pas de vidéo pour le moment, alors voilà une photo de mon chat](https://i.imgur.com/gv9hWgA.png)


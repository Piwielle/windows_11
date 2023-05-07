# Convertir Windows d'hérité vers UEFI

De base, Windows n'est pas forcément installé en mode UEFI, et donc n'est pas forcément compatible avec le Secure boot. Si vous activez le Secure boot sans que Windows soit en mode UEFI, le PC ne démarrera pas. Ce tuto permet de vérifier et régler ça.

## Vérification
Pour vérifier : 

- Appuyer sur les touches <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30"> + <kbd>R</kbd> en même temps pour ouvrir la fenêtre Run.
- Taper dans la fenêtre :

> **msinfo32**

- Appuyer sur entrée.
- Dans la fenêtre qui s'ouvre, chercher la ligne **Mode BIOS**

<img src="https://i.imgur.com/uGYD4Qd.png" width="775" height="290">

Si la ligne dit **Mode BIOS : UEFI** -> Parfait, ton Windows est compatible, tu peux aller activer le Secure boot en allant regarder [la vidéo de la dernière étape.](#activation-du-secure-boot)

Si la ligne dit **Mode BIOS : Hérité** (ou Legacy si ton PC est en anglais), tu dois convertir ton Windows avant de pouvoir faire ça.


## Conversion de Hérité vers UEFI
Pour effectuer cette conversion, quelques étapes assez simples :

- Clic droit sur <img src="https://i.imgur.com/QfAQiaL.png" width="30" height="30">
- Windows Terminal (Admin)
- Copie-colle cette ligne : 

> **mbr2gpt /validate /allowFullOS**

L'invite de commande devrait répondre ces lignes :

```MBR2GPT: Attempting to validate disk 0
MBR2GPT: Retrieving layout of disk
MBR2GPT: Validating layout, disk sector size is: 512 bytes
MBR2GPT: Validation completed successfully
```

Une fois que tu as vu ces 4 lignes, et que tout a marché, tu peux passer à la conversion en coopiant-collant cette ligne : 

> **mbr2gpt /convert /allowFullOS**

L'invite de commande répondra ça :
```
MBR2GPT will now attempt to convert the default book disk.
If conversion is successful the disk can only be booted in GPT mode.
These changes cannot be undone!

MBR2GPT: Attempting to convert disk 0
MBR2GPT: Retrieving layout of disk
MBR2GPT: Validating layout, disk sector size is: 512 bytes
MBR2GPT: Trying to shrink the system partition
MBR2GPT: Trying to shrink the OS partition
MBR2GPT: Creating the EFI system partition
MBR2GPT: Installing the new boot files
MBR2GPT: Performing the layout conversion
MBR2GPT: Migrating default boot entry
MBR2GPT: Adding recovery boot entry
MBR2GPT: Fixing drive letter mapping
MBR2GPT: Conversion completed successfully
MBR2GPT: Before the new system can boot properly you need to switch the firmware to boot to UEFI mode!
```
Une fois ça terminé, c'est tout bon. Windows est maintenant en mode UEFI, et le Secure boot peut être activé sans problème.

## Activation du Secure boot
On peut maintenant aller dans le BIOS, et activer le Secure boot. Le tutoriel pour cette partie est sous forme de vidéo disponible ici :

[<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb">Vidéo sur l'activation du Secure boot @12:09](https://youtu.be/arWlC6HZpTY?t=729)


# Windows 11

Windows 11, pour l'instant, c'est un peu pourri. Y'a des bugs qui réduisent les performances avec les CPU AMD, la barre des tâches est pas vraiment fonctionnelle, l'interface du menu démarrer non plus.

Mais bon, c'est l'avenir. Avec les nouvelles sorties de matériel (salut Alder Lake), et de logiciels/jeux, la meilleure expérience sera sur Windows 11, que ça me plaise ou non.

Je vais lister ici les tweaks que j'utilise pour rendre l'OS un peu plus agréable à utiliser, c'est un peu expérimental, et en cours d'évolution.


## 1/ Le clic droit.

### 1.1/ Activer.

Le clic droit de Windows 11 ressemble à ça : 

![image menu](https://i.imgur.com/l6MxFzI.png)

Alors oui, c'est très joli y'a des icônes. Mais si je veux utiliser 7zip pour extraire une archive, ou alors accéder à mon panneau nvidia, je suis obligé de cliquer sur "Afficher plus d'options", puis sur ce que je veux. C'est pénible.

Pour récupérer le clic droit de Windows 10, il faut modifier une clé de registre, ce qu'on peut faire via le Terminal.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne suivante
```reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

### 1.2/ Annuler le changement.

Pour annuler cette modification, il suffira de faire l'inverse et de supprimer la clé de registre qu'on a modifié.
- Clic droit sur ![menu démarrer](https://i.imgur.com/QfAQiaL.png)
- Windows Terminal (Admin)
- Coller la ligne suivante
```reg delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f```
- Vérifier que la réponse confirme que l'opération a bien été effectuée.
- Redémarrer le PC.

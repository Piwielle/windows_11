# Régler ses problèmes de crash de CG

Tu as des crashs, que ça soit en jeu ou non. Ton écran devient noir, ça ventile fort et il se passe plus rien. Tes jeux se ferment sans rien dire, ou avec un message d'erreur. Tu as des pertes de performances.
Ce genre de problèmes vient **peut-être** des pilotes de ta CG, et des réglages appliqués par défaut dans Windows. On va lister ici des étapes que tu peux suivre qui devraient aider à résoudre ton problème.

## DDU
La première étape consiste à utiliser DDU pour nettoyer proprement ton ancien pilote de CG, et réinstaller la dernière version du pilote officiel en partant d'une base saine. Il est important de l'utiliser en mode sans échec.

Cette vidéo te guidera sur la bonne utilisation de DDU: [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb">Utiliser DDU pour nettoyer proprement son pilote de CG](https://youtu.be/efAjIwAuqYg)
## MPO / TDR / HAGS / ULPS
- MPO
Il s'agit d'une option de Windows qui permet (en simplifiant) de superposer des images 2D et 3D plus rapidement. Connue pour causer des problèmes sur les jeux, des fois. [Plus de détails](https://learn.microsoft.com/en-us/windows-hardware/drivers/display/multiplane-overlay-support). 
- TDR
Il s'agit (en gros) d'une option de windows qui permet de récupérer le contrôle du PC en cas de plantage de la CG ou de son pilote. Connu pour être parfois trop agressif, et déclarer un problème alors que tout va bien. [Plus de détails](https://learn.microsoft.com/en-us/windows-hardware/drivers/display/timeout-detection-and-recovery).
- HAGS
En très gros, ça permet à la CG de décider toute seule comment prioriser les tâches selon les application. Connu poru causer des problèmes avec les jeux et le streaming. [Plus de détails](https://devblogs.microsoft.com/directx/hardware-accelerated-gpu-scheduling/). 
- ULPS
C'est une option spécifique aux pilotes AMD qui permet en théorie d'économiser de l'énergie. Connu pour causer des crashs et des soucis de performances.

Pour désactiver ces 4 options, on va utiliser un logiciel nommé [MPO-GPU-FIX](https://github.com/RedDot-3ND7355/MPO-GPU-FIX)

- Télécharger le logiciel : [clique ici](https://github.com/RedDot-3ND7355/MPO-GPU-FIX/releases/download/Update4/MPOGPUFIX.zip)
- Extrais le logiciel de l'archive (clic droit -> extraire)
- Lance le logiciel puis coche les 4 options, il faut que tout soit rose comme sur l'image.
<img src="https://i.imgur.com/9CIqIme.png" height="304" width="364" alt="Logiciel MPO" class="img-mpo">

Il faut ensuite redémarrer le PC.

## GameDVR

Le paramètre de Windows qui enregistre en permanence ton écran pour pouvoir récupérer les 30 dernières secondes quand tu appuies sur un bouton peut causer des crashs, ou des soucis de performances.

Pour le désactiver : 
- Aller dans les paramètres
- Cliquer sur l'onglet "Gaming" puis le menu "Captures"
- Décocher la case "Enregistrer ce qui se passe"
<img src="https://i.imgur.com/3gH4HBP.png" height="367" width="1053"  alt="captures" class="ccapture">

Il faut ensuite redémarrer le PC.

## Vérifier les connexion physiques.

Dans certains cas, les problèmes peuvent être causés par des connexions électriques pas parfaites entre la CG et le port PCI-E de la carte mère, ou bien entre la CG et les câbles d'alimentation. Pour régler ces problèmes, on peut retirer et remettre la CG dans le PC, et vérifier les câbles d'alimentation.

- Eteindre complètement le PC, et le débrancher de la prise
- Appuyer plusieurs fois sur le bouton démarrer du PC débranché, pour vider les condensateurs
- Retirer la CG de la carte mère (si tu sais pas bien comment faire, regarde cette vidéo: [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb">Retirer la carte graphique d'un PC](https://www.youtube.com/watch?v=LAnjWS35oOA)
- Tant que la CG est retirée, on peut vérifier les connecteurs d'alimentation. Si ta CG n'a qu'un connecteur pour câble d'alim, tu n'as rien à faire c'est forcément bon. Si par contre ta CG a 2 connecteurs, il faut vérifier que tu utilises bien un câble dédié par connecteur de la CG. L'image te montre clairement les choses à faire et à ne pas faire :

<img src="https://i.imgur.com/kZkvhN7.png" height="635" width="757"  alt="cables" class="cables">
- Corrige ensuite les câbles d'alimentation pour en utiliser des séparés, puis remet ta CG dans le PC.

## Autres

Si malgré avoir fait tout ça tu rencontres encore des soucis, le problème peut venir d'ailleurs. Une incompatibilité matérielle, logicielle, un processeur instable, de la RAM instable, un jeu pourri, un problème matériel quelconque...
N'hésite pas à rejoindre le [<img src="https://i.imgur.com/b8g1o9k.png" width="20" height="20" alt="Logo discord" class="img-logo-discord"> Discord d'entraide informatique](https://discord.gg/informatique) et à expliquer ton problème !

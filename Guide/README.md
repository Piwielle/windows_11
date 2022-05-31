# Windows 11
Un guide d'installation et d'optimisation complet et sans risques.

## Créer une clé USB d'installation
La première étape, c'est de créer une clé USB d'installation de Windows, qu'on pourra utiliser pour formater un PC et réinstaller Windows proprement.

### Pré-requis
Pour ça, il nous faut deux choses :
- Accès à un ordinateur fonctionnel sous Windows.

Il est également possible de créer la clé sur Linux via [balenaEtcher](https://www.balena.io/etcher/).
Un outil existe aussi pour MacOS (UNetbootin), mais il n'est pas fiable, on ne vous le recommande pas.

- Une clé USB de 8 Go ou plus.

Si la clé indique 7,X Go, il s'agit bien d'une clé USB de 8 Go, et elle fonctionnera.

### Création de la clé d'installation
Le principe est simple. On va commencer par télécharger l'outil de création de clé de Microsoft, en suivant les opérations suivantes :
- Cliquer sur le [lien vers le site de Microsoft](https://www.microsoft.com/fr-fr/software-download/windows11).
- Se rendre dans la catégorie "**Création d'un support d'installation de Windows 11**".
- Cliquer sur le bouton "**Télécharger**" pour télécharger l'outil.

Une fois l'outil téléchargé, son utilisation est assez simple : 
- Lancer le logiciel.
- Accepter les termes du contrat.
- (Si nécessaire, décocher la case "Utilisez les options recommandées pour ce PC", et changer la langue et/ou l'édition.)
- Appuyer sur le bouton Suivant.
- Sélectionner le média "Disque mémoire flash USB".
- Appuyer sur le bouton Suivant.
- Sélectionner sa clé USB dans la liste. Si elle n'apparaît pas du premier coup, utiliser le bouton "Actualiser la liste des lecteurs".
- Appuyer sur le bouton Suivant.

Une fois ces étapes terminées, la clé va se créer toute seule. L'opération peut prendre du temps selon la connexion, la clé USB, et le PC.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20">`1 - Créer une clé USB d'installation`](https://youtu.be/nidskw_JslQ)

## Installer Windows

La clé étant créée, on va pouvoir l'utiliser pour formater le PC et installer une version fraîche de Windows.

### Démarrer sur l'installateur
On va commencer par retirer la clé USB du PC, et la rebrancher dans un des ports USB de l'arrière, directement sur la carte mère. Ensuite, on va démarrer le PC, **et spammer la touche F11 du clavier pendant le démarrage**.

On arrive ensuite sur un menu de démarrage, qui nous demande sur quel média démarrer le PC. On choisit notre clé USB (**en UEFI si il y en a plusieurs**), et on continue.


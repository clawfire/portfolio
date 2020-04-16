---
layout:	post
title:	"Fixing homebrew on macOS Sierra"
date:	2016-08-07
featured_image: /img/1*KNEboDgw8TxmPjnBqLyxOA.png
---

Une nouvelle version de macOS (bye bye os X au passage) viens forcément tout exploser au niveau de homebrew. Comme toujours. Sans compter que si, comme moi, vous n’aviez pas encore déplacer vos casks depuis `/opt/homebrew-cask/` vers `/usr/local/Caskroom/` cela va nécessiter une petite étape supplémentaire apparemment dû à une restriction des droits sur `/usr/local/`.

### Step 1 : Mettre à jour homebrew

```
brew update
```

### Step 2 : Fixer les droits & réinstaller les build tools

```
sudo chown -R $(whoami) /usr/local
```

A ce moment là vous pouvez aussi vérifier que *brew doctor* ne vous retourne rien de mauvais. Ensuite il faut réinstaller les build tool natifs de macOS :

```
xcode-select --install
```

### Step 3 : Bouger vos casks dans le nouveau répertoire

```
mv /opt/homebrew-cask/Caskroom/* /usr/local/Caskroom/
```

Ensuite vous pouvez virer l’ancien dossier sans remords :

```
rmdir /opt/homebrew-cask/Caskroom
```

Et voila ! Vous pouvez installer sans aucun soucis vos cask et les mettre à jour. Un petit coup de brew upgrade pour la route et vous êtes bon 😉

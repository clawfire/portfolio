---
layout:	post
title:	"OSX 10.11 et l’option sans racine (rootless)"
date:	2015-06-12
featured_image: /img/1*03nkhApNjUPO322eUcDIpw.png
---
Avec la nouvelle version d’OS X, Apple introduit une nouvelle fonction de sécurité : le démarrage sans racine. L’idée est de contrer les malwares en passant certains dossiers comme */usr/bin *ou */usr/local *en immutable.

Il ne semble pas s’agir de ne pas avoir les droits en écriture, d’ailleurs si vous jetez un oeil ses dossiers sont accessibles en écriture. Non il semble que ce soit un nouvel état.

#### Comment faire ?

Plusieurs solutions circulent sur internet notamment celle de désactiver dans la *nvram* l’état *rootless*.


```
sudo nvram boot-args=”rootless=0"
```

#### Et si ça marche pas ?

Malheureusement dans mon cas, même après un reboot je suis toujours en *rootless*. Alors, comment faire ?

Mon souci principal est d’avoir *brew* et *vagrant* de fonctionnel. On peut installer *vagrant* via *cask* avec *brew* comme ceci :


```
brew cask install vagrant
```

Mais avant tout il faut rendre à nouveau */usr/local* accessible en écriture, réinstaller les outils CLI de *xcode* et mettre à jour l’intégralité de *brew*.

Quelques liens pour aller plus loin :

* [Vagrant ne peut plus fonctionner](https://github.com/mitchellh/vagrant-installers/issues/54)
* [Cabal ne fonctionne plus](https://github.com/haskell/cabal/issues/2653)
* [Le thread Reddit qui va bien](https://www.reddit.com/r/apple/comments/3994os/rootless_feature_is_in_os_x_1011_and_it_disallows/)

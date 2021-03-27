---
layout:	post
title:	"scrollTo() jQuery sans plugin ?"
date:	2011-10-27
---

  Aujourd’hui j’ai eu besoin de me passer du (apparemment seul) plugin qui permet de faire un .scrollTo(position) en jQuery pour la simple et bonne raison qu’il plante avec ma méthode de détection de Chrome et du numéro de version.

(oui j’arrive à détecter chrome / safari indépendamment et leur version, et non “webkit”)

Ni une ni deux quelques recherches sur internet et me voilà qui bricole un script **jQuery** natif, qui **n’utilise pas de plugin** et qui permet de **lancer un scroll de l’utilisateur** pour l’amener à **une position précise de la page**, le tout avec une animation.

Voici donc ce que cela donne, j’ai volontairement zappé la structure de la page dans ce code, puisque c’est simplement pour vous montrer comment j’ai procédé, de même qu’il ne faudra pas oublier d’initialiser jQuery & jQuery UI et de faire tourner le bout de code après un $(document).ready() hein ;)

[Voir la démo sur JSFIDDLE](http://jsfiddle.net/clawfire/FKndZ/)

[Crédit Photo](http://www.flickr.com/photos/dmitry-baranovskiy/2378867408/)

  
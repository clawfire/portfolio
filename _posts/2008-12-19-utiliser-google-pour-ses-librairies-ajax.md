---
layout:	post
title:	"Utiliser Google pour ses librairies AJAX"
date:	2008-12-19
---

  Dans un course à l’optimisation, il est toujours intéressant de pouvoir externaliser un service, à condition que le moyen vers lequel on l’externalise soit plus performant que le notre. En pratique, il peut être intéressant d’utiliser des architectures puissantes comme Amazon S3 ou autre pour un accès plus rapide à des média. La règle de base en matière de temps de chargement, c’est que plus c’est proche de l’utilisateur, plus ça sera rapide à charger, et encore plus si c’est en cache !

En temps normal quand vous loadez un Framework AJAX quelconque, vous utilisez cette méthode :

Donc vous chargez le média depuis votre serveur. Consommation de bande passante et surtout latente dépendant de la localisation entre votre serveur et le client de l’internaute au final. Bien alors le concept, c’est de ne pas loader le framework depuis son propre server mais depuis … Google ! Avec tout ses serveurs répartis à travers le monde, qui mieux que google peu être apte à optimiser la distance entre le serveur et le client ? De plus, quand on pense à la bande passante de google, et du fait que tout ceci soit entièrement gratuit, pourquoi s’en priver ? Sans compter que même pour un déploiement en intranet, énormément d’infrastructures autorisent l’accès aux ressources google …

Enfin un des nombreux autres intérêts dont on ne listera pas ici tout les points, c’est que en passant par google, si le client a déjà accédé à un site utilisant cette méthode d’appel de Framework AJAX, son navigateur ira chercher directement la version en cache plutôt que de passer par un re-téléchargement, puisque le fichier est inchangé et présent sur la machine cliente.

Bon maintenant après vous avoir vanté les mérites de cette solution, voici comment l’implémenter en utilisant la fonction google.load() :

Bien que cette méthode marche et soit valide, il semblerais que la fonction google.load() soit un peu longue parfois à s’exécuter. Quand je dis longue je pense a 1.10 de seconde à peine, rien de plus. On peut pour cela un peu cheater et faire donc comme la bonne vieille méthode, à condition de savoir où aller chercher le .js :

Bon tout ca sur le papier c’est bien joli, mais si vous avez envie de tester sans pour autant devoir remplacer tout les appels à la main sur votre blog wordpress, j’ai , encore une fois la solution : le plugin <http://blog.clearskys.net/2008/05/28/google-ajax-libraries-api-plugin/> qui s’installe comme tout plugin wordpress, en deux clics, et qui va remplacer automatiquement TOUT les scripts présents sur les serveurs Google par son équivalent. Car oui, google ne supporte pas que jquery mais une dizaine de framework différents, et peut être bien plus prochainement.

[source](http://blog.websourcing.fr/blog/2008/12/13/optimisez-le-temps-de-chargement-de-vos-pages-en-utilisant-linfrastructure-de-google/)  
[Credit Photo](http://www.flickr.com/photos/thomashawk/256622412/ "Google Code de Thomas Hawk, sur Flickr")

  
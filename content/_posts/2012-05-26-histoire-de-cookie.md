---
layout:	post
title:	"Histoire de Cookie"
date:	2012-05-26
---

  En application de la directive européenne 2009/136/CE transcrites dans plusieurs pays européens (dont la Grande-Bretagne, la France & le Luxembourg) il va être obligatoire de demander à l’internaute sont consentement pour stocker tout cookies qui aurait pour autre finalité que stocker les préférences linguistiques, la mémorisation d’un mot de passe, la résolution d’une video visionné en ligne, un cookie flash ou la mémorisation d’un panier d’achat.

Concrètement la commission européenne souhaite limiter les possibilités de stocker des cookies tierce partie ; qu’ils soient de réseaux sociaux (via la bouton twitter, like de Facebook, +1 de Google, …) ou de régies publicitaires (doubleClick, AdSence, …) et oblige donc les éditeurs de site internet de demander expressément à l’internaute d’autoriser l’implantation de cookie. Ce choix étant mémorisé via un cookie … Comble de l’ironie non ? Surtout quand on pense aux nombreux internautes qui ont pris la bonne habitude de supprimer leurs cookies à la fin de leur session de surf & qui devront donc encore et toujours reconfirmer leur choix …

#### Solution Coté Éditeur

Il existe deja des scripts comme cPrompt pour afficher un message à l’internaute, stocker la réponse dans un cookie s’il n’as pas déjà répondu et afficher les éléments qui vont stocker des cookies dans son navigateur s’il l’autorise. Cependant cela souffre de graves problèmes d’UX. Qui n’as jamais pesté lorsqu’il arrive sur un site et se mange une pop-up / disclamer avant d’accéder au contenu ?

#### Solution Coté Navigateur

Il y a aussi un autre problème selon moi, ce réglage devrait être le fait du navigateur, pas de l’internaute. Pleins de navigateurs permettent deja de choisir entre :

* Accepter tout les cookies
* Accepter les cookies du site mais pas les cookies tiers
* Refuser tout les cookies
Et en plus ils gèrent des listes d’exception. Il suffirait donc de revoir un peu l’interface qui permet de jouer avec ses réglages, comme en facilitant la possibilité d’ajouter des exceptions à la volée.

#### Responsabilité des services tiers

Et concernant les cookies tiers, il me semblerais juste que ce soit au service tiers de requérir l’autorisation de l’internaute de placer des cookies. Cela permettrais de ne pas requérir sur chaque site l’implantation de cookies tiers d’un même service tiers, mais aussi de simplifier l’application de la loi.

#### Mini FAQ

#### Cette loi est elle donc mauvaise ?

En soit non, c’est une belle avancée dans la protection de la vie privée des internautes, il est juste regrettable de voir que sur l’autel de la sécurité on sacrifie l’expérience utilisateur (et qu’une fois de plus on préfère légiférer plutôt qu’éduquer un minimum les gens).

#### Qu’encoure t on ?

Dans les pays où le délais impartit à l’application du dispositif, comme la Grande Bretagne, il vous en coutera £500 000 d’amende. En France comptez €300 000 , mais rassurez vous le délais de mise en place n’est pas encore dépassé.

#### Est ce applicable ?

Personnellement je pense que non. Comme toute lois qui tente de contraindre les Internets, il ne faut pas oublier que le cadre des lois est difficilement mondial, alors que les Internets le sont. Contraindre une partie des Internet n’as pas de sens en soit et est quasi impossible.

#### Est ce contournable ?

Je crois entrevoir une possibilité de contournement de la loi, via notamment ce qui est appelé un “cookie flash”. En effet Flash gère lui même ses cookies dans un espace sandboxé en dehors du navigateur. Ainsi si vous supprimez les cookies de votre navigateur, les cookies flash persistent. Ce n’est pas la seul technologie qui fait cela, Silverlight en fait autant, Java aussi il me semble. Quoi qu’il en soit en autorisant les cookies flash, il suffira aux éditeurs de passer sur ce genre de solutions pour contourner la loi, ou sur [bien pire](http://samy.pl/evercookie/).

#### Plus d’infos

* Plus d’information sur [Owni](http://owni.fr/2012/05/25/aucun-site-ou-presque-ne-respecte-la-loi)
* [Directive Européenne](http://www.legilux.public.lu/leg/directives/archives/2009/2009D0136.html)
* [Transposition dans le droit luxembourgeois](http://www.legilux.public.lu/leg/a/archives/2011/0172/2011A2938A.html)
* [Transposition en droit Francais](http://www.vie-publique.fr/actualite/panorama/ordonnances/ordonnance-du-24-aout-2011-relative-aux-communications-electroniques.html)
* [Plus d’infos sur le script coté site web](http://michaelwright.me/cPrompt)
[Credit Photo](http://www.flickr.com/photos/pomofo/4342155360/)

  
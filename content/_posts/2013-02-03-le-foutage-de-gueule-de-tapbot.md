---
layout:	post
title:	"Le foutage de gueule de Tapbot"
date:	2013-02-03
---

  Comme beaucoup d’utilisateurs de Twitter sur iOS j’utilise TapBot sur mon iPhone et j’en suis ravis. La vison iPad est tout aussi satisfaisante et permet de faire tellement plus que le client Twitter officiel si basique, qui n’as pas été mis à jour depuis plus d’un an à part pour supporter les changements dans les API, qu’il est aujourd’hui impensable que je fasse machine arrière.   
Alors forcément quand Tapbot annonce la bêta de son client pour Mac, je me jette dessus. Même si la première version a l’air d’une alpha, je me plaît a retrouver sur mon ordinateur toutes ses fonctions essentielles comme le filtre des clients Twitter (adieu twitcam), ou les hashtag, sans parler de la possibilité d’utiliser mon propre raccourcissent d’url. Bref je m’égare.

#### Tapbot tu chies dans la colle

On le savait des le début et c’est bien normal, la version finale de Tapbot sera payante. Et j’étais même ravi de payer pour un software de si bonne facture. Seulement comme beaucoup quand j’ai vu le prix, je suis tombé de haut.

**16,00€ pour un client Twitter.**

Mais ce n’est pas tant le prix que sa justification qui me foutent les glandes. En effet Tapbot justifie cela par le fait que les tokens API Twitter sont limités et qu’ils n’auront que peu de temps pour faire leur blé et rentabilise le développement de leur application

#### Les tokens Twitter

Sous couvert de vouloir donner priorités aux applications à forte valeur ajoute, Twitter ne donne plus qu’un nombre limite de token par application, de sorte à empêcher naturellement les clients twitters de prospérer. Parceque oui c’est chiant ses clients twitters qui n’affichent pas la pub que l’on envois via les tweets sponsorises et les trendings topics sponsorises …. Qui sont ils pour se permettre cela. Et en plus ils font mieux que nous avec toujours plus de service et d’ergonomie ? Non mais on a pas acheté tweetie y a 3 ans pour se faire dépassé quand même. Comment ça on n’as abandonné le développement du client officiel depuis plus d’un an ? Et alors ?

Donc voilà, maintenant une application peut être autorisé sur un nombre limite de compte. Et tant que les comptes ne retirent pas les autorisations de l’App sur leur compte, ils bloquent un token.

#### Comment sont gérés les tokens chez tweetbot ?

D’après ce qu’on pouvait lire dans une première version en ligne, Tweetbot gère de manière uniformise ses tokens entre les clients iPhones, iPad et iMac. Choix très judicieux, cela permet de ne consommer qu’un token pour 3 périphériques simultanés.

Cependant dans la justification du prix de l’application, Tapbot revient sur ses propos et annonce que les tokens sont gérés par application ( ils ont donc crées trois applications différentes chez Twitter ) ce qui fait qu’ils prévoient un pic important de nouvelles consommations au fur et a mesures que les utilisateurs arriverons. C’est une stratégie comme une autre, se défaire des utilisateurs existant pour se concentrer que sur les utilisateurs iMac, cela permet de faire repartir les compteurs à zéro.

Enfin pas vraiment. En effet toujours d’après le blog post, les utilisateurs bêta utiliseraient des tokens de l’application iMac et sont priés de révoquer l’application pour les libérer s’ils n’achètent pas l’application finale. Outre le fait que c’est totalement faux puisque nous n’avons pas eu à re-autorise l’application à accéder a notre compte Twitter , ce qui aurais été le cas si ils avaient effectivement fait une nouvelle application chez Twitter pour l’iMac.

Enfin le problème avec cette gestion, c’est qu’il va être assez difficile d’avoir une projection fiable de la consommation des tokens. En partant d’une application avec déjà des tokens consommes, on s’assure de ne pas en re-attribuer et d’avoir un faible taux de nouveaux utilisateurs. Avec une nouvelle application, on va avoir un pic et puis après quoi ? Comment évaluer et prévoir la consommation ? Impossible …

#### La limitation de tokens Twitter, une vrai limitation ?

On peut se poser la question. En effet les solutions ne manquent pas pour palier à ce problème. Comme par exemple contacter Twitter pour leur demander d’augmenter la limite des tokens. Tout simplement. C’est même une des solutions propose par Twitter eux mêmes. Il est également possible de procéder à un enregistrement simplifié & assisté d’une application pour chaque utilisateur, afin qu’ils utilisent leur propre clé API.

Mais non, Tapbot aime se réfugier derrière le grand méchant Twitter ( ce qui n’est pas faux ce l’on moi, Twitter deviens un truc un peu limite gerbant dans son rapport a son écosystème ) mais c’est trop simpliste de leur part. Et c’est décevant de la part d’une société qui a fait de si bon produit, au on aurait été ravis de payer massivement 5€ pour pouvoir l’utiliser sur notre Mac.

#### Une stratégie commerciale

Pur conclure j’évoquerais simplement l’hypothèse commerciale. Le problème n’est pas de l’argent à faire vote rentrer pour rentabiliser l’application, bien au contraire. Le but est d’amortir sur le plus long terme possible l’application. Avec un prix élevé, on réduis la demande pour l’application. Ainsi en restreignant le public, on peut vendre pendant plus longtemps l’application. Donc on est visible plus longtemps.

Et accessoirement on prends nos utilisateurs pour des cons en leur racontant n’importe quoi. Mais ça …

  
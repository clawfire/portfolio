---
layout:	post
title:	"It just works"
date:	2013-10-13
---

  Il y a des sujets parfois délicats dans le monde du travail. Celui de la productivité ou de la qualité du travail fourni en est un.

Il y a des sujets parfois délicats dans le monde de l’informatique. Celui du respect des standards et des bonnes pratiques en est un.

S’il est bon de se fixer pour objectif d’être productif et de respecter les bonnes pratiques lors de notre travail, à nous développeurs informatique, je pense qu’il est bon de garder aussi un oeil sur une métrique importante. Ce que veut le client. Et le fonctionnement de ce que l’on est censé produire.

![Overthinking by Maddi Gabriel - http://flic.kr/p/bECNui](/img/0*7LJwUUFJG9ZlgZSa.jpg)Overthinking by Maddi Gabriel — <http://flic.kr/p/bECNui[/caption]>

**Est-ce que ça fonctionne ?**

La question principale à se poser avant de faire “mieux”. Il faut d’abord faire en sorte que cela fonctionne. Ne pas partir sur trop complexe, ne pas trop anticiper un changement futur ou vouloir trop de maintenabilité. Typiquement, il faut éviter à ce stade de faire du réutilisable. Attention, il n’est pas nécessaire pour autant de faire un truc sale. Bien au contraire. L’idée est de faire un truc qui fonctionne. Un [MVP](http://en.wikipedia.org/wiki/Minimum_viable_product) en quelque sorte.

**Est-ce que cela répond au besoin du client ?**

Deuxième étape, s’assurer que ce qu’on a fait réponds au besoin du client. Pas au besoin qu’on pense que le client va avoir. Pas à celui dont on est sûr qu’il a voulu exprimer. Celui qu’il a exprimé.

**Est-ce qu’on a besoin de faire mieux ?**

Là c’est plus délicat. Il faut prendre en compte plusieurs paramètres, dont le temps restant par rapport au temps estimé. Si le client n’a jamais de temps pour revoir, refacturer et embellir son code; Il est possible, parce que nous avons pris une approche “It Just Work” d’avoir du temps à la fin de la réalisation de notre tache pour retravailler et faire mieux. C’est seulement à ce moment-là qu’on peut revoir le code. Et il n’y a pas de considération du genre “oui, mais on rogne sur notre marge” à avoir. Non. La marge a été ajoutée par rapport à l’estimation que vous avez faite sur cette tache. S’il vous reste du temps, utilisez-le pour faire mieux les choses, tout en conservant votre minimum viable fonctionnel (c’est là que vous pouvez vous amuser avec des branches GIT :) ).

**Facebook et son code procédural immonde**

Il se trouve qu’en 2007 apparemment suite à une mauvaise configuration de leur serveur, le module PHP n’ayant pas été installé une partie du code de [la page d’accueil de Facebook se soit retrouvé exposé](https://gist.github.com/nikcub/3833406). Et il réapparait aujourd’hui sur [un GIST Github](https://gist.github.com/nikcub/3833406) où tout le monde s’empresse de dire “Oh mon dieu que c’est sale” ( sans oublier quelques trolls PHP ). Alors oui c’est du procédural et on pourrait dire que c’est sale. Mais en cela fonctionnait.

Facebook est aujourd’hui le plus grand réseau social du monde qui compte 1 150 millions d’utilisateurs (octobre 2013), cotés en bourse, avec 5 100 millions de revenus en 2012 et dont le rang Alexa est 2, et qui connait sans doute les moindres recoins de votre intimité.

Alors oui c’est peut-être sale. Mais ça fait le job. Et ça le fait plutôt bien, je crois.

  
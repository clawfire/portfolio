---
layout:	post
title:	"Installer SVN 1.7 sur Debian Wheezy"
date:	2014-09-15
---

  Bien que je sois d’accord avec le fait que les gens qui utilisent encore SVN devraient être pendus sur la place publique éduqués quand à l’existence de système décentralisés comme [GIT](http://git-scm.com), mais il arrive parfois que vous aillez besoin de SVN.

Mon cas est assez simple, j’ai un client qui bosse sur un projet open-source avec presque 10 ans d’existence. Il y a donc encore quelques reliquats en SVN qui sont très, mais alors très rarement, mis à jours. Sauf que quand ça arrive et que composer te lâche dans les dents que tu as une version trop vieille de SVN ( 1.6 étant livrée avec Debian ) tu as l’air fin.

Et Debian ne propose pas plus que 1.6.x. Bien que 1.7.x & même 1.8.x existent. Dans mon cas j’ai été assez bête pour mettre à jour vers 1.8.x alors que le dépôt était en 1.7.x . Grossière erreur, ne pouvait checkout le dépôt je ne peux pas le mettre à jour vers 1.8.x et donc pas le checkout ( le serpent qui se mort la queue cette histoire). Ne voulant pas déranger mes collègues, j’ai donc désinstallé SVN 1.8.x et essayé de trouver comme installer SVN en 1.7.x … Du coup petit article pour que tu n’aies plus à chercher, futur moi, et toi aussi qui serait tombé par ici au hasard d’une recherche Google ou d’un flux RSS que tu pensais mort.

[Source](http://s.thibau.lt/XXUZ)

  
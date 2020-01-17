---
layout:	post
title:	"Tagada, le gestionnaire APT-GET indispensable !"
date:	2008-12-08
---

  Alors que je me baladais tranquillement au détour du web je suis tombé sur [ce billet](http://whereisbryan.wordpress.com/2008/08/29/tagada-ou-comment-egayer-la-gestion-de-programmes-en-console/) du blog whereisbryan (rien que le nom me fait presque éclater de rire) qui nous fait découvrir un utilitaire qui nous permet d’utiliser la célèbre commande [apt-get](http://en.wikipedia.org/wiki/Advanced_Packaging_Tool "Advanced Packaging Tool") de manière … différente.

Alors pour ceux qui ne connaissent pas encore, APT-GET est un gestionnaire de paquet pour les distributions linux basée sur debian (ubuntu et tout …) qui permet d’installer, mettre à jour, désinstaller des logiciels. Bref, la commande standard est normalement apt-get install , apt-get remove, etc …

Et bien là, Tagada change la donne :

* pour installer un paquet : tagada tsoin tsoin <nomdupaquet>
* pour mettre à jour les paquets : tagada pouet <nomdupaquet>
* pour supprimer un paquet : tagada pabo <nomdupaquet>
* pour supprimer et purger un paquet : tagada trépabo <nomdupaquet>
* pour chercher un paquet : tagada konépa <nomdupaquet>
Et ce n’est que quelques exemples parmis les fonctions apt supportées ! C’est tellement énorme que Même [la documentation officielle](http://doc.ubuntu-fr.org/tagada) d’Ubuntu mentionne le projet. Si ca vous interesse, rendez vous sur [la page du projet](http://www.codingteam.net/tagada-aff_fr.html) .

![](/img/0*TuQBR5Ca3YZhpDaB.)  
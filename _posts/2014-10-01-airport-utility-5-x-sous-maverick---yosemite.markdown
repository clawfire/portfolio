---
layout:	post
title:	"Airport Utility 5.x sous Maverick & Yosemite"
date:	2014-10-01
---

Alors qu’Apple nous a [supprimé depuis maintenant un bon moment](http://support.apple.com/kb/ht1731) la possibilité de nous servir de notre bonne vieille Airport Express 1ère & seconde génération pour faire un pont entre notre réseau Wi-Fi et le port Ethernet, il se trouve que je ne sois pas tout à fait de cet avis …

Parce que prendre ses clients pour des cons ça va deux minutes. L’airport express a toujours su se comporter comme un client Wi-Fi qui permet de connecter des périphériques sur son port Ethernet, et donc de faire un pont entre les deux interfaces réseaux.

Donc quand Apple viens te dire que ta borne [n’est pas compatible](http://support.apple.com/kb/ht1731) et va [désactiver son interface ethernet](http://support.apple.com/kb/ht1731) si tu l’a connecte en client Wi-Fi, ça m’agace un peu. Surtout que tout cela viens de la mise à jour du logiciel de gestion des bornes Airport qui arrête de prendre en charge cette option de configuration, alors même que le logiciel de la borne, lui même mis à jour, continu d’en être capable.

#### Utiliser l’ancien utilitaire

Ca c’est la solution si vous tournez sous une version d’os x antérieure à Maverick. Il vous suffit d’avoir conserver l’ancien logiciel ou alors de le re-télécharger, il est encore [disponible chez Apple](http://support.apple.com/downloads/#peripherals).

Si par contre tu as fait ta mise à jour vers Maverick ou Yosemite, trop de composants internes à l’OS on été mis à jour, notamment tout le mécanisme de signature du code avec Gatekeeper, et tu ne peux pas installer et / ou utiliser tel quel le logiciel

#### Utiliser un lanceur

[Un mec génial](http://coreyjmahler.com), Corey J. Mahler a eu l’idée, non pas d’aller bidouiller l’exécutable, ce qui serait possible, mais de créer [un lanceur](http://coreyjmahler.com/2013/10/24/airport-utility-5-6-1-on-os-x-10-9-mavericks/) pour que ce dernier ai tout ce dont il ai besoin pour passer Gatekeeper et s’exécuter.

Ce mec est un génie ! Et il nous permet de télécharger gratuitement le [lanceur avec une copie de Airport Utility 5](http://coreyjmahler.com/2013/10/24/airport-utility-5-6-1-on-os-x-10-9-mavericks/) sur son site. Cela fonctionne sur Maverick & Yosemite sans problème. Pensez juste à faire clic droit, ouvrir pour passer Gatekeeper et voila !

J’aimerais juste m’attarder sur un point super important pour moi. Ce mec ne s’est pas contenté de solutionner un problème à l’arrache et de repartager cela avec la communauté, il l’as fait de la bonne façon, sans altérer le logiciel éxistant, de manière à ce que vous puissiez utiliser le votre ou tout simplement vérifier le md5 de l’application originale pour voir que rien n’est modifié. Il le fait de façon à ce que vous puissiez être en confiance, en sécurité, et nous permet de nous rendre compte que plus de choses devraient être faites ainsi.

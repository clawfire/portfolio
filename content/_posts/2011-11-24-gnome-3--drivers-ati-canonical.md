---
layout:	post
title:	"Gnome 3, drivers ATI Canonical"
date:	2011-11-24
---

  Lors d’un précédent article sur l’[installation de Gnome 3 et des drivers qui vont bien](http://thibaultmilan.com/blog/2011/10/17/gnome-shell-ubuntu-oeneiric-driver-ati/ "Gnome-Shell sous Ubuntu Oneiric et driver ATI propriétaires") nous avons vu qu’il fallait compiler/packager nous même nos drivers pour que tout fonctionne et certains lecteurs ont émis des reserves quand à l’update vers des versions futures, stables, distribuées par Canonical et cette méthode.

D’autres se sont également inquiété de bugs qui restaient non résolus avec mon tutos ou de l’impossibilité de tourner sur un nouveau kernel sans devoir repackager le drivers à chaque fois sous peine de voir x11 ne jamais démarrer.

Que tous se rassurent, ils peuvent maintenant mettre a jour les drivers pour repasser sur un canal de distribution “traditionnel” et bénéficier de la résolution de beaucoup de bugs graphiques restant avec l’installation manuelles des drivers de chez ATI. Il suffira de faire tourner les commandes suivantes et d’attendre la réinstallation de tout une tripoté de paquets (et la désinstallation **automatique** des anciens drivers) :

Et voila un reboot plus tard tout fonctionne parfaitement.

  
---
layout:	post
title:	"Update Ubuntu 11.10 Oneiric : Unable to connect to system bus"
date:	2011-10-18
---

  Lors de ma récente mise à jour d’Ubuntu vers 11.10, je me suis retrouvé au reboot suivant avec l’impossibilité de lancer une session. en choisissant au boot une console de récupération je tombe sur un message d’erreur bien étrange :


> Unable to connect to system bus : Fail to connect to socket /var/run/dbus/system\_bus\_socketBon ok et ensuite ? Après quelques recherches il s’avère que lors de la mise à jour de Ubuntu vers 11.10, les dossiers /var/run et /var/lock ont été déplacé vers /run et /run/lock. Cependant dans de rares cas, le script de mise à jour ne crée pas le lien symbolique permettant aux applications non préparés à ce changement de continuer à fonctionner. Il faut donc intervenir manuellement.

[alert-red] Attention, ma responsabilité ne pourra être engagée si d’avenir votre machine se comporte anormalement ou subis un quelconque dommage. Vous effectuez vos manipulations à vos propres risques. [/alert-red]

#### 0. Prérequis

Il vous faudra avant tout arriver à une console, un terminal. Personnellement j’ai au boot choisis de démarrer sur l’option de récupération (recovery) d’Ubuntu. Il vous faudra attendre le message d’erreur et patienter pour que le système vous donne une invite de commande.

[alert-red] Vous aurez besoin des droits ROOT user (administrateur) de votre machine. [/alert-red]

#### 1. Créer les nouveaux répertoires

Attention il est possible que le script de mise à jour ai réussis cette étape. Dans ce cas surtout **ne supprimez pas les répertoires existants.** Passez simplement à l’étape suivante

#### 2. Déplacer le contenu restant vers les nouveaux répertoires

Attention, il est possible que vous ayez besoin de préfixer par sudo.

#### 3. Créer les liens entre les anciens & nouveaux dossiers

On supprime donc les anciens répertoires afin de créer des liens symboliques, véritables raccourcis qui permettrons aux application codées pour aller chercher dans les anciens répertoires de trouver le contenu en toute transparence.

Et voila il ne vous reste plus qu’a redémmarer votre machine et tout devrais fonctionner à nouveaux.

Source :

* [[ubuntu] unable to connect to system bus — Ubuntu Forums](http://ubuntuforums.org/showthread.php?t=1590618)
* [Bug #811441 in dbus (Ubuntu): “Unable to connect to the system bus: Failed to connect to socket /var/run/dbus/system\_bus\_socket: Connection refused (oneiric)”](https://bugs.launchpad.net/ubuntu/+source/dbus/+bug/811441)
  
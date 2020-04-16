---
layout:	post
title:	"Case Sensitive & Mac OSX"
date:	2013-05-10
---

  Cet article est le premier d’une série concernant mon environnement de développement. Aujourd’hui nous allons aborder le cas du [système de fichier sensible à la casse](http://fr.wikipedia.org/wiki/Sensibilit%C3%A9_%C3%A0_la_casse "Voir sur Wikipédia"). PHP est sensible à la casse et de ce fait lorsque vous chargez des fichiers il faut faire attention à la casse dans le nom du fichier mais aussi dans le nom utilisé dans votre code. Sinon vous allez développer, tester, croire que tout passe et une fois déployé BAM ! Tout explose.

### Pourquoi ?

Pourquoi Mac OS est case insensitive ? Cela semble être une conner bétise sans nom non ? Historiquement Mac OS (< OS X) était case insensitive mais préservait la casse. Depuis Léopard (peut être Tiger même) la gestion des File System Case Sensitive à été ajouté à l’utilitaire disque (alors que HFS+ supporte le case sensitive depuis Panther). Cependant certaines applications ne sont pas compatible avec de tels systèmes de fichiers comme FileMaker Pro ou World of Warcraft (qui ne tourne sous aucun FS Case Sensitive d’ailleurs …). Et puis soyons sérieux. Pour le commun des mortels le case sensitive c’est juste … pain in the ass

### Créer un conteneur Case Sensitive

Plutot que de reformater tout votre disque en HFS+ sensible à la casse , ce que vous pouvez tout a fait faire avec l’utilitaire disque, je vous propose de créer un conteneur sensible à la casse pour y stocker vos fichiers de dev.

1. Ouvrez l’utilitaire disque
2. Choisissez nouvelle image
![Utilitaire Disque - Nouvelle Image](/img/0*ICdOGR6FvWEQQj_Q.png)1. Sélectionnez la taille maxi (ici 4.6 Go nous suffira)
2. Sélectionnez Un format sensible à la casse (journalisé si vous le souhaitez, pour vous servir de TimeMachine plus facilement)
![File System Case Sensitive](/img/0*j3DwjfLuoNZj66k8.png)1. Format SparseBundle. Cela nous permettra de ne prendre que la place nécessaire sur le disque, donc éviter de pré-allouer l’espace ;)
![Les points à vérifier](/img/0*KqGNc3J4navmZUgx.png)Après cela vous choisissez où l’enregistrer, cela n’as pas vraiment d’importance.

### Monter le conteneur

Le montage de toute image disque sur OSX est aussi simple qu’un double clic. Sauf que cela ne nous laisse pas le choix du point de montage. Ce qui n’est pas du tout pratique.

#### Une fois

L’utilitaire hdiutil nous permet de faire cela en ligne de commande :

#### Au démarrage

La première fois je me suis dit “hey si je faisais un script automator ?” . Je peux en faire un .app qui peut être lancé au démarrage et dans les actions disponibles je peux exécuter un script shell (celui ci dessus) donc ça me paraissait pas trop mal. Et puis je me suis dit qu’on pouvait optimiser cela nan ? Les manipulations suivantes sont à faire avec votre image montée (double cliquez dessus simplement), peu importe où.

Maintenant vous pouvez éjecter votre volume et l’ajouter à vos éléments de démarrage via les Préférences Système, Utilisateurs et groupes , Ouverture . Voila :)

[Credit Photo](http://www.flickr.com/photos/35805601@N07/6946546976/)

  
---
language: fr
published: true
category: talks
layout: talk
date: 2021-03-04 20:00:00 +0100
title: "#nocode Thursday: Simple contact tracing"
description: ''
featured_image: "/img/2021/04/copie-de-fluo-vert-et-violet-lego-twitch-banniere.png"
event_link: https://www.twitch.tv/thibault_nocode
location:
  name: "#nocode Thursday"
  url: https://www.notion.so/nocode-Thursday-f3cc13b34cd94d479e9f0f915fc637cc

---
Pour cette session nous allons partir sur un sujet d’actualité, une application de 🦠 contact tracing #covid19 relativement simple. L'idée est de coller aux obligations faites dans plusieurs pays, notamment en 🇧🇪Belgique, de collecter les données des clients qui viennent en point de présence physique. Sauf que, tenir un registre papier ou demander aux gens de remplir un billet sur formulaire papier à donner ensuite aux équipes de ventes (coucou KFC) c'est vraiment pas top en temps de pandémie non?

On va donc faire un truc assez simple:

1. Tout commencera avec un QR code qui permettra de lancer l’app. Il pourra être placé à l’entrée ou alors sur chaque table. Il y aura un champs libre sur le QR code où le responsable de l’établissement pourra mettre un numéro de place.
2. Le client saisi ses coordonnées pour la traçabilité. On lui confirme l’enregistrement par email.
3. 21 jours plus tard, comme on aime bien respecter la 🇪🇺 #GDPR, on supprime automatiquement ses donnés. On pourra lui envoyer un email aussi pour lui confirmer (et travailler au passage la confiance du client dans la marque).

J'ai aussi rencontré ce genre de dispositif à l’aéroport d’ 🇳🇱 Amsterdam l'année dernière et j’ai trouvé cela super bien fait, simple et rapide d’utilisation. C’était sur base volontaire mais j’ai participé de bon coeur.

En attendant, si vous voulez un peu tester Glide, je vous propose de commencer ici [https://www.glideapps.com/r/baMac2hqbxPgACaVLPnR](https://www.glideapps.com/r/baMac2hqbxPgACaVLPnR "https://www.glideapps.com/r/baMac2hqbxPgACaVLPnR") (lien affilié, non rémunéré).
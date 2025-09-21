---
language: fr
published: true
layout: talk
date: 2021-03-11 20:00:00 +0100
title: "#nocode Thursday: Simple contact tracing"
description: ''
featured_image: "/img/2021/04/copie-de-fluo-vert-et-violet-lego-twitch-banniere.png"
event_link: https://www.twitch.tv/thibault_nocode
location:
  name: "#nocode Thursday"
  url: https://www.notion.so/nocode-Thursday-f3cc13b34cd94d479e9f0f915fc637cc

---
Tout les jeudis, j'organise [un stream sur Twitch](http://twitch.tv/thibault_nocode) où j'explore une des idées ci-dessous et construit, à l'aide d'outil no-code ou low-code une solution. C'est l'occasion de vous faire découvrir ou re-découvrir des outils simples et intuitifs pour démarrer vos projets, mais aussi d'avoir des conversations franches à propos des limites qui peuvent exister.

***

Pour cette session, on va continuer avec l'app de 🦠 contact tracing que l'on a conçue la semaine dernière et on va explorer comment ajouter un peu de logique, d'automatisation, à l'aide de plusieurs outils.

* Zapier, plateforme vous permettant d'executer des "actions" à la suite de "déclencheurs"
* Google App Script, qui permet en écrivant quelques lignes de code de manipuler rapidement notre feuille Google Spreadsheet

Vous l'aurez compris, ici nous mettrons en parallèle une approche purement no-code avec une approche low-code.

📱L'app de la semaine dernière [est dispo ici](https://contacttracing.glideapp.io) si vous voulez jouer avec en attendant-

[La feuille Google Spreadsheet est dispo ici]()

[Ici vous trouverez le "zap" utilisé](https://zapier.com/shared/2ad0e66265f81d765f3600c99850192d27118596) par l'app pour supprimer automatiquement les données au bout de 21 jours. Vous pouvez le copier mais il vous faudra un compte payant (même le plus petit) pour utiliser le multi-step.

[Et le code pour le Google App Script est le suivant](https://gist.github.com/clawfire/dc215283007e258f16d4e20c027540be) (avec en 1er mon petit fichier utilitaire).

{% gist dc215283007e258f16d4e20c027540be %}
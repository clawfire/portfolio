---
layout:	post
title:	"Mobilité Décentralisé"
date:	2016-06-17
featured_image: /img/1*-KnujJK5mPWsDl_IOPhnHA.png
---

Ce weekend j’ai participé à un hackathon à [Level2](http://level2.lu) qui se trouvait être un “B-Side”. Mon interprétation de ce terme, appliqué au Hackathon sera “alternatif” dans le sens DIY, fun, sans se prendre vraiment au sérieux. Ca a donc été l’occasion de retrouver des partenaires de code, et de faire naitre un petit projet qui me trottait dans la tête depuis un moment.

## Mobilité centralisé

Il existe un organisme au Grand Duché, nommé la [centrale de la mobilité](http://mobiliteit.lu) dont le but est assez vague pour le public. De manière pragmatique, c’est une identité visuelle commune aux solutions de mobilité douce (bus, train, vélo, …). Ils fournissent aussi un centre d’appel pour de l’assistance. Enfin. Assistance est un bien grand mot. Disons qu’il vont plutôt faire des recherches pour vous sur leur site internet concernant des horaires. Si vous appelez pour demander des renseignements sur un retard, ou pire, vous plaindre, vous serez toujours accueillis par un “ce n’est pas nous, on ne sait pas”.

Couramment donc, je me plains sur Twitter des retards des bus / trains au Grand Duché en mentionnant la centrale de la mobilité puisqu’ils assument le rôle de communication centralisé. Bon, twitter pour eux c’est un flux RSS, ils l’indiquent d’ailleurs, [aucune réponse ne vous sera donné et vous ne serez même pas lu](https://twitter.com/mobiliteit_lu).

## Décentraliser tout cela

Puisque l’organisme en charge de centraliser les informations n’offre pas à nous, utilisateur, satisfactions, nous avons décidé de nous ré-approprier la chaine de signalement.

Présentation qui ne se prends pas trop au sérieux du concept#### Comment cela fonctionne ?

Comme nous n’avions que 48h, et que les compétences en développement faisait défaut, nous sommes partit sur [Typeform](http://typeform.com) qui permet de faire de magnifiques formulaire qui passent super bien sur mobile, très riche & interactifs.

![](/img/1*oyuR-cdC_syCwbztvVY-8Q.png)

Comme on ne voulais pas payer un compte pro+ pour envoyer les données vers un autre service web (via webhook) on a utilisé [Zapier](https://zapier.com/). C’est une sorte de IFTT, on manipule des blocs logiques qui font des choses.

*Exemple :* A chaque nouvel enregistrement dans le formulaire Typeform, envoyer certaines données à un service web (webhook).

![](/img/1*fANzKVeQDIWqnIet03UZPg.png)

Les données arrivent donc dans un service web, [Stamplay](https://editor.stamplay.com/register?refCode=41289e26) . Stamplay c’est un service (encore un) qui permet de ne plus avoir de backend. Le backend est la partie cachée d’une application web. Et bien plutôt que de devoir la développer, on va utiliser un service qui nous permet de faire (je ne liste que ce qu’on a utilisé) :

* Sauver des données dans une base de données et les lire
* Manipuler des données ( via du code NodeJS )
* Créer des workflow de fonctionnement de manière graphique

{% include post-components/gallery.html
	columns = 2
	full_width = true
	images = "/img/1*9h1FccjhF3KcYJyxjOLgbg.png,/img/1*bHk7jsW6H-boKvtRSrJhvQ.png"
%}

_Gestion des utilisateur (y compris via facebook et twitter connect), modèle de données, stockage des données, workflows dans Stamplay._

{% include post-components/gallery.html
	columns = 2
	full_width = true
	images = "/img/1*202uPohDA8EUkK_NvPlIaA.png,/img/1*ZOGo8FV_2HUCrnxBIRmjdQ.png"
%}

A ce stade, nous avons donc, sans avoir écrit une ligne de code, créé un formulaire permettant de saisir des données sur un rapport et de les transmettre à un système de stockage, qui va permettre de servir les données via une API, le tout automatiquement.

Reste donc à faire la partie affichage des rapports. J’ai utilisé [EmberJS](https://guides.emberjs.com/) pour sa simplicité à utiliser les résultats d’une API directement comme modèle, et [SemanticUI](http://semantic-ui.com/) qui apporte une touche moins “vu partout” que Bootstrap. Le code est disponible sous [licence MIT](https://github.com/clawfire/mobiliteit-decentral/blob/master/LICENSE) sur Github.

[clawfire/mobiliteit-decentral](https://github.com/clawfire/mobiliteit-decentral)

En plus de la liste des rapport, j’ai également commencé, sans avoir eu le temps de finaliser, une page permettant aux administrations d’indiquer que les rapports sont traités.


{% include post-components/gallery.html
	columns = 2
	full_width = true
	images = "/img/1*-KnujJK5mPWsDl_IOPhnHA.png,/img/1*HmViP18hWJb4jCJA7RedDw.png"
%}

_La page d’acceuil qui affiche la liste des rapports & Le détail d’un rapport_

## What’s next ?

Est ce qu’on va continuer le projet ? Oui je pense. Il ne reste plus grand chose à faire pour que cela soit opérationnel et que l’on puisse le mettre en ligne.

Coté amélioration, j’aimerais remplacer le formulaire Typeform par une page de l’application qui liste les données, afin de pouvoir récupérer plus facilement la géolocalisation (et ne pas se baser uniquement sur les données EXIF de la photo) ainsi que pouvoir de manière interactive suggérer arrêt, ligne et n° de bus à l’utilisateur qui complète un rapport.

Et vous ? Qu’aimeriez vous avoir ?

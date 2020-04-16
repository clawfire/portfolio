---
layout:	post
title:	"Collections dans Jekyll et filtre where_exp"
date:	2018-01-14
featured_image: /img/1*tLIXa6jWWjxfB-6AYjm2Hg.jpeg
---

Après avoir acheté un thème à 20 $ sur [Themeforest](https://themeforest.net/?ref=clawfire) histoire de dire qu’on a un travail assez pro (OK le code HTML & CSS ne sont pas toujours supra propres, mais ça fait le job largement) pour le site de mon mec, [DJ José Sanchez](http://djsanchez.eu).

Dans un premier temps j’ai modifié la page HTML et uploadé le tout sur un hosting Gandi vite fait bien fait. Mais la mise à jour, c’est un truc chiant, on ne va pas se mentir. Tout ce qui est contenu qui a propension à expirer assez rapidement et à être produit en quantité va donc nécessiter beaucoup de travail.

J’ai donc choisi d’utiliser Jekyll pour gérer le contenu, un truc de base et rapide donc, que je peux utiliser depuis n’importe quel périphérique avec une connexion internet et mon accès GIT.

Bref, un petit coup de `jekyll new` et hop on a les bases. On créé des helpers, on fait un fichier `home.html` de layout et hop. J’ai reproduit le site.

### Les Collections

Les collections c’est un truc super pratique de Jekyll qui permet de faire plus que des pages et des posts. Il suffit de déclarer dans le `config.yml` la collection comme suit :

```
collection
    - events
```
Ensuite il suffit de mettre vos fichiers `.md` dans un dossier `_events` dans mon cas (donc `_` + nom de la collection) et tout sera dispo dans `site.events` (donc `site.[collectionName]`).

### Itérer sur les collections

La manière la plus simple est de faire un `{%- raw -%}{% for event in site.events %}{% endraw %}` (une boucle) et on récupère dans event les infos de chaque fichier `.md` et les données du FrontMatter.

Mais dans mon cas je voudrais pouvoir :

1. Trier par date (bah oui ce sont des évènements)
2. N’afficher seulement que les évènements qui ne sont pas passés. Pour cela on pourra compter sur la variable site.time qui renvoie la datetime actuelle.

Pour atteindre cela on doit passer par le stockage dans une variable intermédiaire, via `{%- raw -%}{% assign ... %}{% endraw %}` . Cette fonction supporter qu’on la chaine avec des filtres.

Le filtre `| sort: ...` est la réponse à mon premier point. En effet par défaut c’est le nom de fichier `.md` qui donne l’ordre. Et à moins d’être à 100% sur de se donner une hygiène de convention de nommage, il est plus sur de trier.

Le filtre `| where: ...` semble de prime abord être une bonne solution. Mais il ne permet qu’une comparaison avec l’opération `==` . Dans mon cas j’ai besoin d’utiliser `>=` . Mais pas de panique, Jekyll inclus depuis quelques versions maintenant le filtre `| where_exp: ...` qui va nous donner tout ce que l’on veut.

#### where_exp

Alors OK, mais comment il marche ce super filtre ? Parce que la documentation est quand même super chiche sur le sujet. C’est très accès “it just works” …

Sauf que dans mon cas, cela ne marchait pas … car je n’avais pas compris que le premier argument devait être la variable dans laquelle on va pouvoir effectuer une comparaison. Je soupçonne d’ailleurs que cette variable puisse être soumise à collision. Dans l’exemple ci-dessous, j’avais utilisé event à la place de item et cela ne marchait plus du tout.

Ci-dessous, le code fonctionnel pour ne prendre que les évènements non encore passés et triés par date :

```
{%- raw -%}
{% assign eventList = site.events | where_exp: 'item', 'item.date >= site.time' | sort: 'date' %}
{% for event in eventList %}
<!-- Do your stuff here -->
{% endfor %}
{% endraw %}
```

### That’s it !

Ce post vous a aidé ? N’hésitez pas à me le dire sur [Twitter](https://twitter.com/thibaultmilan) , à commenter et partager cet article sur tout vos réseaux 😉.

Photo by [Kevin](https://unsplash.com/photos/w7ZyuGYNpRQ?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/code?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

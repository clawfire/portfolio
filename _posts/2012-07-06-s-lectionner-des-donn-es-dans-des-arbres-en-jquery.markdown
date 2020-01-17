---
layout:	post
title:	"Sélectionner des données dans des arbres en jQuery"
date:	2012-07-06
---

  Le besoin du jour rencontré dans le cadre de mon travail chez [absolu payment](http://www.absolu-payment.com/fr/) est d’avoir une méthode de sélection multiple de donnée dans une liste, depuis un arbre de données.

Ne pouvant utiliser <optiongroup> puisque bien que le W3C encourage les user agents à supporter une version imbriquée (*nested*) en pratique aucun navigateur ne supporte cela à ce jour, impossible donc d’avoir une balise autre que <option>.

Découverte après quelques recherches du très bon plugin intégré plus ou moins à bootstrap, [chosen](http://harvesthq.github.com/chosen/), malheureusement celui ci se base sur une implémentation à base de <optiongroup> et l’on retombe vite sur les mêmes problématiques.

Autre option plus ou moins satisfaisante, passer par des select boxs multiples, générés dynamiquement, avec un [plugin jQuery](http://kotowicz.net/jquery-option-tree/demo/demo.html) très bien fait. Possible mais écarté du fait de l’encombrement que va vite prendre cette solution si l’on veux pouvoir sélectionner plusieurs éléments.

Après quelques recherches supplémentaires, je tombe sur le plugin [jstree](http://www.jstree.com) qui permet de manipuler un arbre de données (typiquement ce que j’ai en termes de structure de données et qui semble parfaitement convenir à mes besoins, d’autant que celui ci supporte :

* Un flux d’entrée en [JSON](http://www.jstree.com/documentation/json_data), XML ou HTML
* Du [multi-checkbox](http://www.jstree.com/documentation/checkbox)
* La possibilité d’[internationaliser](http://www.jstree.com/documentation/languages) les champs affichés
  
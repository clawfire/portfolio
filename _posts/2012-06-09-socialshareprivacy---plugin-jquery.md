---
layout:	post
title:	"SocialSharePrivacy , plugin jQuery"
date:	2012-06-09
---

  [Précédemment](http://thibaultmilan.com/blog/2012/05/26/cookie-directive-europeenne/) je vous ai parlé des problématiques de cookies qui surviennent ses derniers temps en Europe. Et nous avons découvert quelques solutions pratiques, généralistes.

Cependant, on peut aussi voir la problématique d’un point de vue confidentialité. En effet, comme on l’as vu , les réseaux sociaux comme Google+, Twitter & Facebook tracent notre activité via les boutons de partage. Et en tant que distributeur de contenu, éditeur de site, etc … nous souhaitons peut être permettre à nos lecteurs de faire le choix de se faire “fliquer” ou non; de ne pas leur imposer cela par défaut.

Dans cette optique, j’ai découvert récemment le plugin jQuery [SocialSharePrivacy](http://www.heise.de/extras/socialshareprivacy/) qui permet d’afficher une version désactivée des boutons Twitter, Facebook & Google+ , que l’utilisateur pourra activer via un interrupteur. A ce moment là le (ou tous) “vrai” bouton de partage est chargé et l’utilisateur peut l’utiliser comme d’habitude. De plus un cookie est enregistré pour se rappeler du choix de l’utilisateur d’activer tel ou tel bouton de partage sur votre site (oui sinon ça deviendrais vite chiant). Et comme c’est une action utilisateur qui déclenche l’enregistrement du cookie, [les nouvelles restrictions que l’on à vu précédemment](http://thibaultmilan.com/blog/2012/05/26/cookie-directive-europeenne/) ne s’appliquent pas. Elle est pas belle la vie ?

Bon donc voila, je vous faire découvrir le plugin mais vous vous rendez compte que tout est en allemand. Comme la licence est une MIT, je me suis dit que je pourrais faire un fork en anglais / français et le proposer librement, sous cette même licence. Mais bon, seulement si certains d’entre vous y manifestent un intérêt certains, sinon … Donc n’hésitez pas à me dire si cela vous intéresse en commentaire.

**EDIT :** Apparement il existe deja une version anglaise sur [github](https://github.com/patrickheck/socialshareprivacy)

  
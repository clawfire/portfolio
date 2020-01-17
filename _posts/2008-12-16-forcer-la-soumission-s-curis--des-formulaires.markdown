---
layout:	post
title:	"Forcer la soumission sécurisé des formulaires"
date:	2008-12-16
---

  Lorsque l’on fait un site tout **sécurisé**, genre e-commerce, il y a souvent un truc qui flanche dans la chaîne du tout sécuritaire, c’est l’envoi du formulaire. En effet les pages on beau être en https, certains transferts peuvent planter, en fait certains navigateurs peuvent ne pas traiter l’**action url** en mode sécurisé, alors que toute la page est ok.

Le plus simple reste de changer le **submit url** du formulaire, mais si l’on utilise un cms, un gestionnaire de caddie ou autre ce n’est pas toujours évident, c’est pourquoi on peut utiliser une petit bout de JS qui va forcer le passage sur une url https plutôt que http pour le** form submit**.

$(function(){  
 var $form = $("form#specificForm");  
 var newAction = $form.attr("action");  
 newAction = newAction.replace(/http/,"https");  
 $form.attr("action", newAction);  
});Et voila grâce à ce petit bout de code va aller chercher le sélecteur, récupéré la variable à changer et effectuer la modification.

Merci [CSS-trick](http://css-tricks.com/force-secure-form-submission/)

  
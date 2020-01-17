---
layout:	post
title:	"Utiliser localStorage sur tout les navigateurs"
date:	2012-09-19
---

  ### Introduction

Avec l’arrivée d’HTML5, de superbes nouvelles techniques trop cool ont débarqués. **LocalStorage** en fait partit. **LocalStorage** permet de stocker sur la machine de l’utilisateur, dans une sandbox accessible uniquement par le site qui crée les données, des données pour ensuite les lires / éditer / supprimer.


> “Tu veux dire comme des cookies ?”Pas vraiment non. **LocalStorage** s’affranchit des limites des cookies ( 4kb max de donnée, chargement a chaque fois des données même si on ne s’en sert pas). De plus, puisque les cookies ont longtemps été utilisé pour espionner les gens, de plus en plus les désactivent dans leur navigateur, ou les efface. Du coup on perd les données enregistrés par effet de bord à cause des annonceurs peu scrupuleux (mais bon c’est leur boulot après tout). **LocalStorage** ne connaît pas ce problème.

[alert-green] Vous pouvez aller à la fin de la page pour retrouver un screencast qui couvre l’essentiel des points que j’aborde ici. [/alert-green]

### Comment ça marche ?

C’est juste le truc le plus simple que j’ai jamais vu en javascript. Il suffit d’utiliser les méthodes setItem() et getItem() .

* Si l’on veut stocker bar dans foo : localStorage.setItem(‘foo’,’bar’);
* Si l’on veut lire la valeur foo : var foo = localStorage.getItem(‘foo’); // -> “bar”
* Si l’on veut supprimer une valeur ? : localStorage.removeItem(‘foo’);
Voila c’est aussi simple.

### Persistance des données

Les données que l’on mets dans **LocalStorage** persistent tant qu’elles ne sont pas retirées par le site ou l’utilisateur, si vous voulez utiliser des données valables pour une session, devinez quoi ? Il suffit d’utiliser **sessionStorage** .

### Compatibilités et problèmes rencontrés

Ok ça semble être juste super simple et magique, mais vous allez me demander où est le piège ?

1. Ce n’est disponible que sur les navigateurs modernes , exit FF 2 et IE6 (plus d’infos sur la compatibilité ici)
2. C’est un stockage clé/valeur texte. Ce n’est pas du JSON. Exit la possibilité de typer ce que l’on stocke  
Solutions
Si l’on avait juste à composer avec le fait de ne pas pouvoir stocker des données typées, je vous aurais recommandé d’utiliser JSON.stringify() et JSON.parse() afin de faire une sorte de sérialisation et de pouvoir conserver vos types. Mais l’on doit aussi composer avec le problème des anciens navigateurs, et il n’est pas question de passer par des cookies (on cherche à ne pas avoir de req. serveur pour cela, et de ne pas recharger les données a chaque chargement de page je vous rappelle !) . Comment faire ?

C’est là que Store.js arrive à la rescousse. Ce petit wrapper va nous permettre non seulement d’être compatible avec tout les navigateurs (oui oui tous, même IE6 … bon ok mais pas lynx ni netscape 2 ) mais aussi de sérialiser / déréaliser à la volée les données que l’on enregistre. Et sans rien perdre de la facilité d’utilisation de **localStorage** :

// Store 'marcus' at 'username'  
store.set('username', 'marcus')  
// Get 'username'  
store.get('username')   
// Remove 'username'   
store.remove('username')   
// Clear all keys  
store.clear()   
// Store an object literal - store.js uses JSON.stringify under the hood  
store.set('user', { name: 'marcus', likes: 'javascript' })   
// Get the stored object - store.js uses JSON.parse under the hood   
var user = store.get('user')  
alert(user.name + ' likes ' + user.likes)Pour la peine je vous partage même une petite video qui montre comment s’en servir (mais bon on vient d’en faire le tour, c’est plus pour l’aspect “hey cool un screencast”).

[localStorage and Store.js](http://vimeo.com/44159609) from [The JavaScript Playground](http://vimeo.com/javascript) on [Vimeo](http://vimeo.com).

[alert-white] Cet article a été écris dans le cadre de mon travail pour [VA Consulting](http://vaconsulting.lu "Expertise PHP & Zend Framework")[/alert-white]

  
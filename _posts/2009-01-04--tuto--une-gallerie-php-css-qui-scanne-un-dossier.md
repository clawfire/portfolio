---
layout:	post
title:	"[TUTO] Une gallerie PHP/CSS qui scanne un dossier"
date:	2009-01-04
---

  Avec mes cours (ridiculeusement peu intéressant je dois l’admettre), on à du faire l’autre jour une petite galerie en HTML/CSS mais pas un truc sympa, juste quelque chose où on entre les images en dur dans le code. Alors j’ai pensé à optimiser un peu ça, en passant tout en PHP pour pouvoir scanner le contenu d’un dossier et tout faire tout seul, sympa non ?

### Comment ça va marcher ?

C’est simple, prenez une capture d’écran de ce qui vous voulez ajouter, d’une taille de 500px par 350px et placez là dans le dossier images/featured, puis une image plus petite qui sera utilisé comme preview, de 50px par 50px. Placez là dans images/tn .

### Le Code HTML/PHP

Scanning Directories with PHP### Some Portfolio

$featured\_dir = 'images/featured/';  
 $scan = scandir($featured\_dir);  
 echo '';  
 ?>$dir = 'images/tn/';  
 $scan = scandir($dir);for ($i=0; $i if ($scan[$i] != '.' && $scan[$i] != '..') {  
 echo '';  
 }  
 }  
 ?>### La CSS

html  
{  
 background: #828282 url(images/bg.jpg) no-repeat 50% 0;  
}body  
{  
 font-family: helvetica, georgia, sans-serif;  
 text-align: center;  
}#container  
{  
 text-align: left;  
 width: 500px;  
 margin: auto;  
}#container h1  
{  
 color: #474747;  
 margin: .4em 0;  
}#featured  
{  
 position: relative;  
 height: 378px;  
 overflow: hidden; /* might remove */  
}#featured h2  
{  
 position: absolute;  
 bottom: 0;  
 margin: 0;  
 line-height: 1.3em;  
 padding: .2em;  
 background: black;  
 color: white;  
 text-align: center;  
 width: 100%;  
 filter: alpha(opacity=60);  
 -moz-opacity: 60;  
 opacity: .6;  
}ul#options  
{  
 background: #e3e3e3 url(images/bottom.jpg) repeat-x 0 100%;  
 overflow: hidden;  
 height: 1%;  
 margin: 1em 0 0 0;  
 padding: .5em;  
 border-top: 1px solid #8a8a8a;  
 border-bottom: 1px solid #f5f5f5;  
}#options li  
{  
 float: left;  
 width: 60px;  
 height: 60px;  
 list-style: none;  
 cursor: pointer;  
}#options li:hover img  
{  
 border: 2px solid gray;  
}#options li img  
{  
 width: 50px;  
}.selected  
{  
 border: 2px solid gray;  
}#options a  
{  
 outline: none;  
}a img  
{  
 border: none;  
}IE6 sucksBa oui IE6 va vous poser des problèmes, si vous avez vraiment envie de parfaire la chose, il suffit de compenser le fait que un élément flottant va contenir des éléments non flottants. Les navigateurs modernes compense cela magnifiquement bien avec un overflow:hidden; mais pour IE6 il faudra ajouter ceci à votre feuille de style :ul#options {  
...le style deja en place...  
height: 1%;  
}### Le Javascript

$(function() {  
 $.preloadImage = function(path) {  
 $("#featured img").attr("src", path);  
 }$('ul#options li img').click(function() {  
 $('ul li img').removeClass('selected');  
 $(this).addClass('selected');var imageName = $(this).attr('alt');$.preloadImage('images/featured/' + imageName);var chopped = imageName.split('.');  
 $('#featured h2').remove();  
 $('#featured')  
 .prepend('' + chopped[0] + '').children('h2').fadeIn(500).fadeTo(200, .6);  
 });$('ul#options li a').click(function() {  
 return false;  
 });  
});FinalementVoila, vous avez un truc sympa qui marche avec Jquery (mon framework ajax préféré au passage). si vous utilisez ce script, merci de faire un ptit retour, ca peut servir. Un grand merci aussi à [Nettuts](http://nettuts.com/videos/screencasts/scanning-folders-with-php/), très bon site de tutos, dont lequel je me suis librement inspiré (voire totalement) mais pourquoi ré-inventer la roue quand ça existe déjà ?  
---
layout:	post
title:	"Switcher entre CSS en PHP"
date:	2009-01-02
---

  Quand on développe des thèmes, des sites, des services web, on a souvent envie de proposer plusieures css, et il faut donc un moyen de pouvoir switcher entre les différentes css. Nous allons voir comment switcher entre plusieurs css dans ce mini tuto, avec une bonne dose de PHP, pas un gramme de JS et sans prise de tête !

### Etape 1 : Mémoriser les styles

La première étape consiste à créer un nouveau fichier sur votre server, nommé switcher.php dans lequels vous mettez le code suivant :

setcookie ('sitestyle', $set, time()+31536000,'/', 'yourdomain.com', '0');  
header("Location: $HTTP\_REFERER");  
?>Lorsqu’il sera appelé, ce fichier écrira un cookie avec les détails concernant le style préféré par l’utilisateur. Bien sur tout cela se passe du coté invisible de la force, l’utilisateur final ne verra rien de ce fichier. Attention à ne pas oublier de remplacer “yourdomain.com” par votre nom de domaine sous peine que le cookie ne fonctionne pas correctement !

Appeler ce fichier est super simple, il vous suffira d’utiliser des liens comme vous en avez déjà fait des centaines surrement :

[clic ici pour passer au style RED !](./switcher.php?set=red)Dans notre cas donc, “red” est le nom de la feuille de style que l’on veut appeler. Pas besoin de mettre le “.css” à la fin, on va s’en charger en automatique par la suite. Notre lien appelle donc le switcher et lui demande de passer sur le “RED”, en laissant donc le switcher faire tout le travail comme un grand. Une alternative aux liens HREF est d’utiliser un formulaire pour sélectionner entre plusieurs styles sans avoir plusieurs liens :

DefaultCrazy RedExperimental Style### Etape 2 : Détection des styles

Laisser les utilisateurs choisir le style qu’ils souhaitent utiliser c’est bien, mais récupérer ce choix une fois mémorisé dans le cookie, c’est mieux ! Ainsi, pour chaque page de votre site qui doit utiliser une feuille de style définie par l’utilisateur, il vous faudra inclure ce code dans la zone <head> de vos pages :

(!$sitestyle)?'defaultstyle':$sitestyle ?>.css">;Attention, ce code est en une seule ligne ! De plus si vous ressentez le besoin d’utiliser le nom de la feuille de style utilisé, vous pouvez utiliser le code PHP suivant :

;Notre petit script va donc détecter le style présent dans le cookie de l’utilisateur et afficher le résultat. Si rien n’est définit il va charger defaultstyle.css, vous êtes bien sur tout a fait libre de changer “defaultstyle” par ce que vous voulez :D

Voila vous êtes l’heureux possesseur d’une solution fonctionnant sur toute plateforme, tout os, tout navigateur, rétro compatible et futuro compatible (oui j’invente des mots ? Et alors ?), bref un ptit bout de code léger qui va bien.

N’hésitez pas à me donner votre avis sur ce tutos, c’est un des premiers que je vais, je suis preneur de toute idée pour l’améliorer.

  
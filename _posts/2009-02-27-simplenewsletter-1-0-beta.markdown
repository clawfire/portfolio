---
layout:	post
title:	"SimpleNewsletter 1.0 beta"
date:	2009-02-27
---

  Voila en attendant une page dédié, je publie ici un petit script de newsletter tout bête. Il va aller chercher une page web et l’expédier par mail. Idéal si vous souhaitez gérer une newsletter avec un simple template personnalisé via votre CMS que vous utilisez tout les jours.En pratique, vous décompressez l’archive sur votre serveur, naviguez vers ./install et suivez les instructions !

#### 2 modes de fonctionnement :

1. Vous passez par la page d’acceuil index.php et pouvez modifier le titre de l’objet du mail tout à loisir
2. Vous accedez à la page ./core/send.php via une tache cron. L’objet sera automatiquement “Newsletter du [DATE DU JOUR]”
Pour le moment l’importation des contacts se fait via un fichier ./importer.php qui va aller chercher un fichier texte pour sauvegarder toute les adresses mails s’y trouvant.

Le fichier doit s’appeler list.txt et comporter une adresse email par ligne. Les doublons ne seront pas importés !

#### Fonctionnalités à venir :

* Configurateur afin déviter l’edition du fichier de config
* Optimisation de l’importateur afin qu’il fasse moins de requêtes à la BDD
* Plugin Wordpress
* Importer depuis une bdd existante
#### Téléchargement

[Télécharger SimpleNewsletter Version 1.0 Beta ZIP](http://thibaultmilan.com/wp-content/uploads/2009/02/simplenewsletter-10-beta.zip)

  
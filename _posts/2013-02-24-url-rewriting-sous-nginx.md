---
layout:	post
title:	"URL Rewriting sous NGINX"
date:	2013-02-24
---

  Suite à mon post sur [l’installation de NGINX](http://thibaultmilan.com/blog/2012/09/16/installer-nginx-avec-php5/) avec le support de PHP5, il est intéressant de voir comment faire ce qu’on fait le plus souvent avec un .htaccess sous Apache : de l’url rewriting.

#### Pourquoi de ne pas juste utiliser un .htaccess ?

Si la question semble pertinente de prime abord, la page qui [réponds à cette question](http://wiki.nginx.org/LikeApache-htaccess) sur le wiki de NGINX démontre qu’il n’en est rien. En effet utiliser un .htaccess c’est comme se tirer une balle dans le pieds dans notre recherche de rapidité. Imaginez. A chaque appel de page, le serveur doit aller chercher dans tout les dossiers et sous dossiers du site à la recherche de fichiers .htaccess pour aller les parser et interpréter leur contenu, en fusionnant les instructions avec la config du serveur, celle de php et les éventuels autres fichiers .htaccess.

Voyez la perte de temps …

#### Le module Rewrite

Comme on peut le voir dans la [documentation concernant le mod rewrite](http://wiki.nginx.org/HttpRewriteModule) de NGINX, la syntaxe est assez simple à utiliser. A base de if suivit d’une confition et de quelques mots clés, il est alors assez simple de mettre en place ses propres règles, directement dans le fichier vhost de votre domaine, dans la section server.

#### Conversion automatique

Mais pour les plus frileux / fainéants d’entre nous , il existe un outil qui se charge de faire notre conversion tout seul et de nous donner les instructions à insérer dans notre vhost. Il s’agit de [apache2nginx](https://github.com/mow/apache2nginx) disponible sur github sous licence libre ( pas de précision sur quelle licence, mais c’est une condition nécessaire il me semble ) et il existe un page en ligne [prêt à l’emploi](http://www.anilcetin.com/convert-apache-htaccess-to-nginx/).

  
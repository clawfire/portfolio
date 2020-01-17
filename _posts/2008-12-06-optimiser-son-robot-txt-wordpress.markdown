---
layout:	post
title:	"Optimiser son robot.txt Wordpress"
date:	2008-12-06
---

  On est tous dingue de référencement, que l’on l’admette ou non. Et dans cette course à l’optimisation du contenu pour un indexage optimale, [Google](http://google.com "Google") [avait déjà publié un livret blanc pour nous aider](http://www.nowhereelse.fr/google-nous-rappelle-les-bases-de-loptimisation-du-rfrencement-12895/). Un des points importants de cette optimisation est la bonne rédaction du fichier robot.txt. ce petit fichier va en effet définir les droits que vous donnez aux robots d’indexion de google, mais aussi des autres, gràce à l’[user-agent](http://en.wikipedia.org/wiki/User_agent "User agent").

Lorsqu’on utilise un blog, [Wordpress](http://wordpress.org "WordPress") mais aussi autre, on est souvent confronté à des adresses multiples pour un seul article. Alors certes des plugins existent afin d’éviter que les robots interprètent cela comme du duplicate content, en utilisant de la ré-écriture d’url, mais dans un soucis toujours d’être bien sur de ce qui se passe, voici un fichier type de robot.txt qui interdit notamment l’accès aux fichiers sources (le cœur) de Wordpress (qui normalement n’est plus indexé puisque necessite une identification, mais bon là encore, prudence). De plus les urls alternatives, commentaires, tracbacks et compagnies seront également exclues de l’indexage.

User-agent: *  
Disallow: /cgi-bin  
Disallow: /wp-admin  
Disallow: /wp-includes  
Disallow: /wp-content/plugins  
Disallow: /wp-content/cache  
Disallow: /wp-content/themes  
Disallow: /trackback  
Disallow: /feed  
Disallow: /comments  
Disallow: /category/*/*  
Disallow: */trackback  
Disallow: */feed  
Disallow: */comments  
Disallow: /*?*  
Disallow: /*?  
Allow: /wp-content/uploads# Google Image  
User-agent: Googlebot-Image  
Disallow:  
Allow: /*# Google AdSense  
User-agent: Mediapartners-Google*  
Disallow:  
Allow: /*# Internet Archiver Wayback Machine  
User-agent: ia\_archiver  
Disallow: /# digg mirror  
User-agent: duggmirror  
Disallow: /Sitemap: <http://www.domain.tld/sitemap.xml>Merci à [Parenthèse.be](http://www.parenthese.be/2008/12/03/wordpress-seo-optimiser-le-fichier-robotstxt/) pour l’info !

![](/img/0*1UlHgzqHgFax-XvF.)  
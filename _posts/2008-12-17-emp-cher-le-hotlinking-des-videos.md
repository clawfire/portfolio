---
layout:	post
title:	"Empêcher le hotlinking des videos"
date:	2008-12-17
---

  Ca nous arrive tous un jour, on se fait hotlinker les images ou les videos. Concernant les images on verra cela plus tard, aujourd’hui c’est des vidéos que l’on va parler. On peut penser que un mec qui nous pompe une video e direct streaming ce n’est pas bien gràve, le problème c’est que ce genre de pratique se généralise de plus en plus. Voici donc une manière simple et radicale d’empecher se bordel qui risque de vous pomper toute votre bande passante et de générer des frais de dépassement de celle ci.

Ouvrez ou créez un fichier .htaccess à la racine de votre site/blog/autre et insérez y ceci :

RewriteEngine On  
RewriteCond %{HTTP\_REFERER} !^$  
RewriteCond %{HTTP\_REFERER} !^http://domain.fr/.*$ [NC]  
RewriteCond %{HTTP\_REFERER} !^http://(www\.)?netvibes.com(/)?.*$ [NC]  
RewriteCond %{HTTP\_REFERER} !^http://(www\.)?google.fr(/)?.*$ [NC]  
RewriteCond %{HTTP\_REFERER} !^http://(www\.)?google.com(/)?.*$ [NC]  
RewriteCond %{HTTP\_REFERER} !^http://(www\.)?netvibes.com(/)?.*$ [NC]  
RewriteCond %{HTTP\_REFERER} !^http://(www\.)?google.fr(/)?.*$ [NC]  
RewriteCond %{HTTP\_REFERER} !^https//feeds.feedburner.com(/)?.*$ [NC]  
RewriteRule .*\.(flv)$ <http://domain.tld/videoalternative.flv> [NC,R,L]Passons aux explications :

* La 1er ligne est optionnelle, en effet elle peut déjà être présente dans votre fichier htaccess, cependant si elle ne l’est pas il faut la mettre pour activer la ré-écriture d’url (url rewriting).
* Les lignes 3 à 9 correspondents aux sites que l’on souhaite autoriser à afficher les video, à savoir votre site et les principaux services comme google reader, netvibes et feedburner
* La dernière ligne stipule que toute demande de fichier flv (on peut le remplacer par un autre format de fichier) par un site qui n’est pas dans la liste renverra vers, et l’on précise une autre vidéo.
On enregistre le tout, on upload, on vide son cache et tadaaa la video s’affiche correctement sur votre site mais pas ailleurs !

  
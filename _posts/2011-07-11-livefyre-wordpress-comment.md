---
layout:	post
title:	"Livefyre Wordpress Comment"
date:	2011-07-11
---

  Vous devez tous connaître Disqus, géant du commentaire non auto-hébergé, vous proposant de centraliser tous les commentaires fait sur les différentes plateformes sociales (blog, twitter, facebook, …). Et bien j’ai découvert il y a peu Livefyre. Un peu dans le même esprit (centralisé & externalisé) le service offre des commentaires en temps réels avec la possibilité pour vos utilisateurs de s’identifier avec leur compte google, facebook ou twitter (ou leur compte sur votre plateforme comme “avant”). Disposant également de fonctions de partage twitter / facebook lors du post des commentaires j’ai été tout de suite séduit par l’interface plutôt clean et clairement moins lourde que Disqus.

Pour un projet d’empowebo.com j’ai donc été amené à voir ce qu’on pouvais faire avec eux niveau intégration et il se trouve qu’ils ont quelques fonctions de Single Sign On plutôt intéressante quand on veut utiliser ses propres accès api à twitter et facebook et ne pas dupliquer les identifications sur ses services pour nos utilisateurs. Acte donc, si un plugin Wordpress existe pour les versions standard, rien n’existe pour les versions un peu plus “prenium”.

#### Livefyre Wordpress Comment

Acte donc, je me suis lancé dans le développement d’un plugin wordpress alternatif à la version officielle. Alternatif car il n’as pas pour vocation de remplacer le plugin officiel et n’intégrera même pas dans les premières versions un support des comptes basiques.

#### Fonctions :

Dans l’ordre des priorités

* Replacement des commentaires wordpress
* Synchronisation des utilisateurs wordpress avec le Remote Profile Managment de Livefyre
* Création d’un endpoint pour le RPM afin de fournir au format JSON les infos des utilisateurs
* Auto-Enregistrement du site et auto-configuration du plugin
* Forcer l’utilisateur à être identifié / s’enregistrer
* Utiliser Facebook et Twitter pour se connecter et partager
* Supporter les comptes free et prenium
#### Suivre le projet

Si vous souhaitez contribuer ou simplement suivre le projet :

[Voir sur Github](https://github.com/clawfire/livefyre-customdomain-wordpress-plugin)

Attention, la branche principale corresponds à la branche de dev, il faudra attendre des tag de version pour avoir une version fonctionnelle.

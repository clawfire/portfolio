---
layout:	post
title:	"Formater en CLI sous OSX"
date:	2019-03-02
featured_image: /img/0*zBxNbhJ0Q0ypgCwJ.jpeg
---
## Comment virer cette putain de partition Linux invisible par mon OS de ma clé USB et récupérer sa taille d’origine

TL;DR; vous pouvez utiliser diskutil eraseDisk \[format] \[nom] \[disk] pour formater tout un disque avec un seul nouveau volume dans un format spécifique.

Tout à commencé quand j’ai monté le Google Voice Kit qu’on a commandé au boulot et que j’ai voulu jouer avec. Comme je suis plutôt studieux j’ai suivi les conseils du guide et j’ai été chercher la dernière image de la carte SD pour reflasher celle préchargée livrée avec le kit. Sauf que, comme je débutais avec Etcher (un super soft pour flasher des cartes) et que leur UX est un peu spéciale, j’ai commencé à flasher ma carte SD et une clé USB qui était branchée également.

Du coup, j’annule, je débranche la clé, flash uniquement la carte SD et me dit que je verrais ce souci de clé plus tard.

Plus tard donc, je découvre que OSX « cache » à l’utilisateur (du moins en interface graphique) les partitions Linux. Impossible de reformater ma clé et de récupérer ses 8 Go depuis Utilitaire Disque. Donc je me suis tourné vers une solution en ligne de commande. Et j’ai un peu cherché.

Tout d’abord il s’agit de trouver sous quelle référence votre disque (votre clé USB / Carte SD / whatever) est monté. Rien de plus simple on lance l’Utilitaire Disque, on sélectionne un des Volumes sur ce disque à gauche et on regarde la référence que je vous ai mise en rouge ci-après.

![](/img/1*sDRuwoo8auadUKU-SGF1KA.png)

_Dans le cas présent ce sera donc le *disk2, s1 indiquant que le volume C SD est en 1er position sur le disque.*_

OK donc maintenant on lance un terminal et on va manipuler Utilitaire Disque en ligne de commande (car il est 20x plus puissant en CLI qu’en interface graphique).

diskutil list va vous permettre de confirmer le disque que vous allez utiliser, en vous indiquant les volumes qui y sont présents, et ce, même ceux que l’interface graphique ne voit pas 🙏🏼

diskutil eraseDisk exfat Trololo disk2 va me permettre de tout récupérer en moins de temps qu’il n’en faut pour le dire. J’explique. Je formate donc tout le disque disk2 en un seul volume au format exfat que j’appelle Trololo.

Voilà c’est tout, c’était plutôt rapide, mais je pense que ça peut dépanner certains d’entre vous un jour. Si vous avez apprécié mon article, vous pouvez le partager sur vos réseaux, ça me fera plaisir.

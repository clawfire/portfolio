---
layout:	post
title:	"iPhone Apps Gratuites ?"
date:	2009-01-10
---

  C’est en effet ce qu’il est possible de faire en théorie. Comment vous allez me dire ? Tout simplement en patchant le fichier d’installation des Applications présent dans votre iPhone ou votre iPod.

### Pré-requis

Alors il va vous falloir remplir quelques conditions :

* Un iPhone ou un iPod Touch Jailbreaké
* Avoir installé OpenSSH (Dans Cydia : Rechercher -> OpenSSH)
* Un client FTP supportant le FTP over SSH (pour Windows et Linux : [FileZilla](http://www.filezilla.fr/), pour Mac : [CyberDuck](http://cyberduck.ch/) ou [Transmit](http://www.panic.com/transmit/))
### Prêt ? C’est partit !

1. Connectez vous en SSH et déplacez vous vers /System/Library/PrivateFrameworks/MobileInstallation.framework/
2. Renommez le fichier Mobileinstallation en Mobileinstallation.bak , ca nous permettera d’avoir une sauvegarde en cas de plantage
3. Téléchargez le fichier Mobileinstallation qui va bien [ici](http://rapidshare.com/files/181651425/2.1.MI.patched.zip) , et placez le dans le dossier où l’on vient de renommer le fichier.
4. Changez les permissions du fichier en 777.
5. Si vous avez déjà patché Mobileinstallation par le passé, cela devrais être bon, sinon allez dans /var/mobile et créez un dossier Documents.
6. Donnez lui les permissions 777.
7. Redemarrez l’iPhone / iPod Touch (indispensable)
### Et Maintenant ?

Et bien maintenant il ne vous reste plus qu’a glisser des fichiers .ipa vers iTunes et lancer la synchro. Le nouveau Mobileinstallation les installera automatiquement et tout bien, sans poser de problème.

### Ok mais mes apps gratos ?

En principe, il ne vous manque plus qu’à trouver des fichiers .ipa et les glisser/déposer dans iTunes pour les installer. PAs besoin de vous rappeler que télécharger c’est mal, qu’il faut payer ses apps et tout. On pourra dire donc que cette méthode permet d’installer des apps dont les développeurs n’ont pas les moyens de payer l’inscription sur l’appStore.

Credit photo : [crazyoctopus](http://www.flickr.com/photos/crazyoctopus/5334337561/ "iPhone 4 jailbreak de crazyoctopus, sur Flickr")

  
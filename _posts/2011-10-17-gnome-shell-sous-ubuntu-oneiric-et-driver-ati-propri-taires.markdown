---
layout:	post
title:	"Gnome-Shell sous Ubuntu Oneiric et driver ATI propriétaires"
date:	2011-10-17
---

  Si comme moi vous êtes (aussi) sous Ubuntu et que vous venez de passer sur Ubuntu Oneiric 11.10 , vous avez peut être voulu tester gnome-shell (gnome 3) mais vous vous êtes heurté à divers bugs graphiques dont une police floue / cryptée et une barre de tache arc en ciel. Pas de panique non seulement on sait d’ou viens le problème, mais aussi comment le résoudre.

[alert-red] Attention, ma responsabilité ne pourra être engagée si d’avenir votre machine se comporte anormalement ou subis un quelconque dommage. Vous effectuez vos manipulations à vos propres risques. [/alert-red]

#### Situer le problème : Les drivers Propriétaires ATI & Unity

Si l’on en crois les nombreux retours que l’on peut lire sur internet concernant cette mise à jour, deux problèmes apparaissent :

1. Unity crée des fichiers de configuration qui interfèrent avec Gnome-shell
2. Il manque une couche d’abstraction de rendu dans les dépendances de Gnome-shell
3. Les drivers ATI pré-compilé sont foireux
Voyons donc comment en 3 étapes simples on répare tout cela …

#### 1. Installer Mutter

première manipulation, on va installer Mutter, qui semble être une couche d’abstraction entre la carte graphique et gnome-shell, un peu comme compiz pour Unity.

[alert-orange] Pensez à activer les dépos universe, multiverse et les partner canonical. [/alert-orange]

Ensuite on remplace Compiz par Mutter pour le rendu de l’image. Votre écran devrais clignoter quelques fois et se stabiliser.

#### 2. Désinstaller toutes traces de drivers propriétaires

Afin de supprimer toutes traces de précédentes installations et téléchargements, lancez ses deux commandes l’unes après l’autre :

#### 3. Télécharger, Compiler & Installer les drivers ATI Propriétaires

Il va falloir oublier ici l’installation classique en ligne de commande ou via l’interface graphique dont vous pouvez être familier, pour télécharger les sources et compiler vous même le driver. Vous allez voir c’est très simple, rassurez vous.

[alert-orange] Pensez à activer les dépos universe, multiverse et les partner canonical. (Paramètres Systèmes -> système -> Sources de logiciels) [/alert-orange]

Si vous êtes sur une architecture 64 bits , il faudra aussi ajouter :

Ensuite on crée un .deb pour l’installer , puis on l’installe :

#### 4. Réinitialisation de la configuration du gestionnaire de fenetre

Et voila. il ne vous reste plus qu’a initialiser une nouvelle configuration de X11, le moteur de rendu des fenêtres puis de vous déconnecter / reconnecter ou redemarrer pour que les changements prennent effet.

Malheureusement, il n’est pas possible de générer à coup sùr une configuration qui réponde à vos besoins (multi-écran, rotation d’écran …); c’est pourquoi je vous partage un exemple ci dessous pour un dualscreen d’écran de même taille. Vous pouvez faire un tour du coté de[ ce site pour avoir quelques exemples](http://wiki.cchtml.com/index.php/Ubuntu_Oneiric_Installation_Guide#Generate_a_new_.2Fetc.2FX11.2Fxorg.conf_file "Unofficial AMD linux community"), et que je remercie au passage pour leur tuto en anglais. Le fichier à modifier est bien sur /etc/X11/xorg.conf , notez au passage que la commande précédente vous a fait une copie de votre ancienne config, dont vous pouvez vous inspirer voir copier coller des pans entiers :)

Sources :

1. [Wiki CCHTML](http://wiki.cchtml.com/index.php/Ubuntu_Oneiric_Installation_Guide)
2. [Forum Ubuntu : Gnome Shell bug d’affichage](http://forum.ubuntu-fr.org/viewtopic.php?id=668531)
3. [Forum Ubuntu : Ubuntu 11.10 et gnome 3](http://forum.ubuntu-fr.org/viewtopic.php?id=669731)
  
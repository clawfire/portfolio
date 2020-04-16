---
layout:	post
title:	"Firefox OS sur mon Nexus 5"
date:	2014-11-01
featured_image: /img/0*dA3_yA5S57uodToN.jpeg
---

A cause de [Paris Web](http://paris-web.com) la semaine dernière, j’ai été conditionné grâce aux metres de stickers ( facile 10 mètre ) Firefox OS à vouloir tester cet OS mobile. D’ailleurs si vous en voulez, un petit commentaire , un [petit mail](mailto://stickersFirefoxOs@thibaultmilan.com) où tu me laisse ton adresse et hop !

Je savais qu’il était possible de l’installer sur mon Nexus 5 et je m’étais laissé dire qu’il y avait même un build officiel de la ROM pour Nexus 5.

**MENSONGES**. Le Nexus 5 n’[est que Tiers 3](https://developer.mozilla.org/en-US/Firefox_OS/Firefox_OS_build_prerequisites) ce qui veut dire qu’il recevra des mises à jours pour corriger ses problèmes spécifiques avec FirefoxOS que si les périphériques Tiers 1 ( ceux qui ont nativement FirefoxOS ) et Tiers 2 ( le Samsung Nexus S qui va juste avoir 5 ans ).

**1er reproche :** Cibler des téléphones de pauvre ou obsolètes. Faire un peu son libriste élitiste snob qui ne veux pas trop que tu utilise son projet tu comprends. Il le fait pour lui et c’est deja super qu’il te laisse poser le regard dessus. Tu devrais être subjugué par l’honneur qu’il te fais. Lors d’une récente interview, les gars en charge du projet chez Mozilla annonçaient qu’il ne sert à rien d’être le 3e OS, qu’ils visent la seconde place, pour commencer. Mais mec si tu pense que des gens vont acheter des téléphones bas de gamme juste pour avoir Firefox OS tu te fou le doigt dans l’oeil et tu traverse ta tête … Espérons que celle liste évolue.

#### Faire une sauvegarde de vos applications & réglages

Connectez votre téléphone en USB et avec adb :

adb backup -apk -shared -allSi vous n’avez pas ADB : brew install android-platform-tools

Plus tard vous pourrez restaurer au besoin via

adb restore backup.ab#### Débloquer son bootloader

Si ce n’est pas déjà fait vous devrez déverrouiller le bootloader

adb reboot bootloader
fastboot oem unlockSuivez les instructions sur votre téléphone. **Cela effacera toutes les données du téléphone pour des raisons de sécurité évidentes**

#### Rootez votre Nexus 5

Personnellement le mien l’était deja depuis un moment mais vous pouvez utiliser [CF-Auto-Root](http://cfautoroot.com) si vous êtes sous Windows. La version pour Nexus 5 se trouve [ici](http://www.devfiles.co/download/dEHWyjmo/CF-Auto-Root-hammerhead-hammerhead-nexus5.zip). En utilisant fastboot vous faites :

unzip CF-Auto-Root-hammerhead-hammerhead-nexus5.zip
fastboot boot image/CF-Auto-Root-hammerhead-hammerhead-nexus5.imgIl ne vous reste plus qu’à suivre les instructions

#### Pré-requis pour Compiler FirefoxOS

Le Mozilla Developper Network a publié des [instructions pour la compilation](https://developer.mozilla.org/en-US/Firefox_OS/Building_and_installing_Firefox_OS). En gros il vous faut :

* Git
* gpg
* ccache
* yasm
* autoconf 2.13
* gcc 4.6
* gnu-tar
* homebrew
Pour cela Mozilla mets à disposition un script :

curl -fsSL <https://raw.github.com/mozilla-b2g/B2G/master/scripts/bootstrap-mac.sh> | bash**2e reproche :** Pourquoi fixer des versions ? Surtout pour autoconf. Ca fait juste chier les gens qui, comme moi, on deja autoconf d’installé … Du coup sur OSX Yosemite j’ai en plus du installer gcc 4.6 avec [brew](http://brew.sh) brew install gcc46
et changer la version de autoconf car je l’avais deja installé et il était déjà à jour :

brew tap homebrew/versions
brew unlink autoconf
brew link autoconf123Notez que si vous n’avez pas xCode, il faudra l’installer. Il est gratuit sur l’app store. Si vous obtenez un message comme quoi votre version n’est pas à jour, vérifiez avec la commande xcode-select -print-path si vous n’obtenez pas /Developer . Si c’est le cas, pas de panique, la commande suivante arrangera tout :

sudo xcode-select -switch /Applications/Xcode.app#### Pré-requis pour OSX

OSX c’est génial tout ça tout ça, mais le système de fichier est, par défaut, insensible à la casse. Pas de quoi fouetter un chat, surtout quand on sait que Adobe n’est pas foutu de faire fonctionner Creative Cloud sur un système de fichier sensible à la casse …

Pourtant si, ~~comme moi~~ vous êtes développeur vous pouvez avoir vite de mauvaises surprises avec les systèmes de fichiers insensible à la casse. Et compiler FirefoxOS ne va pas faire exception. Mais bon pas de panique, [cela me connais maintenant](http://thibaultmilan.com/blog/2013/05/10/case-sensitive-mac-osx/).

Nous allons d’abord créer un volume sensible à la casse

hdiutil create -volname 'firefoxos' -type SPARSE -fs 'Case-sensitive Journaled HFS+' -size 40g ~/firefoxos.sparseimageEnsuite on la monte & on se positionne dedans

open ~/firefoxos.sparseimage
cd /Volumes/firefoxos/**Si vous êtes sous Montain Lion** et que vous recevez une erreur lors de l’installation des dépendances un petit coup de brew install mpfr — use-gcc devrait résoudre votre problème. Relancez la commande qui plante.

#### Compiler FirefoxOS (enfin)

Les commandes suivantes vont cloner le dépôt github de FirefoxOS, configurer le build pour Nexus 5, et enfin lancer la compilation. Attention, à ce moment là vous allez télécharger l’entièreté des Internets et lancer une simulation de la vie sur votre ordinateur. Non sérieusement j’ai bien du mettre 1h pour tout télécharger et 30min pour builder. Prenez un café, lisez un bouquin, glandez … ça va être long.

git clone git://github.com/mozilla-b2g/B2G b2g
cd b2g
./config.sh nexus-5
PRODUCTION=1 MOZILLA\_OFFICIAL=1 ./build.shSi tout se passe bien maintenant vous êtes en posession de quoi flasher votre téléphone avec adb et fastboot. Mais je ne voulais pas l’installer en écrasant mon OS mais juste le tester, alors on va créer une archive pour [MultiROM Manager](https://play.google.com/store/apps/details?id=com.tassadar.multirommgr) (Installez et lancer l’app pour suivre la procédure d’installation).

#### Créer la ROM Firefox OS pour MultiROM Manager

On commence par créer un dossier et copier ce dont on a besoin dedans

mkdir rom
cd rom
rsync -rL ../out/target/product/hammerhead/system .
rsync -rL ../out/target/product/hammerhead/data .
cp ../out/target/product/hammerhead/boot.img .Pour information ici on utilise rsync pour éviter de copier les symlinks mais bien les fichiers liés. Il semble qu’il y ai des bugs sinon mais je n’ai pas trop compris pourquoi.

Ensuite une ROM Android a besoin d’un dossier META-INF qui contient le nécessaire pour effectuer l’installation / mise a jour. Les commandes suivantes vont créer ce dossier, y copier le script ainsi que le lanceur.

mkdir -p META-INF/com/google/android/
cp ../tools/update-tools/bin/gonk/update-binary META-INF/com/google/android/
curl <http://bluishcoder.co.nz/b2g/updater-script> >META-INF/com/google/android/updater-scriptLe script de mise à jour est celui de [bluishcoder](http://bluishcoder.co.nz/2014/06/11/dual-booting-android-and-firefox-os.html) et fonctionne très bien.

Enfin dernière étape, créer le zip qui va bien

zip -r9 b2g.zip *
java -jar ../prebuilts/sdk/tools/lib/signapk.jar
 ../build/target/product/security/testkey.x509.pem
 ../build/target/product/security/testkey.pk8
 b2g.zip signed\_b2g.zip
adb push signed\_b2g.zip /sdcard/TADAAAAA ! Vous avez votre zip poussé sur votre carte SD (ou le répertoire virtuel correspondant). Il n’y a plus qu’a utiliser MultiROM Manager pour l’installer et configurer le multi-boot.

Commencez par redémarrer votre téléphone avec adb reboot recovery, choisissez Advanced puis MultiROM et enfin Add ROM. Suivez les indications à l’écran en prenant soin de sélectionner Android, votre ZIP et zou !

Lors de vos prochains boot, par défaut au bout de quelques secondes votre téléphone démarrera votre OS régulier mais vous pourrez choisir Cancel pour sélectionner ce nouvel OS (nommé au départ signed\_b2g.zip).

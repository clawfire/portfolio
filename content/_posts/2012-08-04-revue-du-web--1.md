---
layout:	post
title:	"Revue du Web #1"
date:	2012-08-04
---

  Beaucoup beaucoup d’actualité cette semaine, et peu de temps pour parler en détails de chaque, mais je voulais tout de même partager ma revue du web, la première ici. Au programme : révolution de l’email tel qu’on le conçoit et que l’on l’utilise aujourd’hui, Premiers outils google drive, Mountain lion & son lot de ressource pour mieux comprendre PowerNap mais aussi assurer une transition en douceur entre growl et le centre de notification, en passant par la ré-activation du partage web.

### Clients Emails

Avec [l’Acquisition de Sparrow par Google](#) récemment le paysage des clients emails alternatifs, innocents et bien pensé semblais être réduit au néant (NDLR : Thunderbird arrêtant son dev, il ne restait que MS Outlook, osX Mail ou Eudora … #Eudoratroll). Cela était sans compter sur quelques projets qui emmerdent parsi par là .

#### [Mailpilot](http://mail-pilot.com)

Mailpilot est le fruit de la réflexion de deux jeunes entrepreneurs / développeurs de 21 ans (je réalise qu’en perspective, je suis vieux … mon dieu … bref) sur le mode de consommation actuel de l’email, et là façon dont il doit se réinventer s’il veut survivre dans notre quotidien ou le temps nous est compté & où lire ses emails devient une corvée. Je vous laisse découvrir sur leur site la via [kickstarter](http://www.kickstarter.com/projects/1380180715/mail-pilot-email-reimagined "kickstarter"), car oui tout est partit de ce magnifique site une fois de plus :)

![](/img/0*3unfLqi-4iF838TC.png)#### [.Mail](http://dotmailapp.com)


> Emails aren’t just emails anymore. Mark as read is useless & not fit for a modern creative workflowC’est ce qu’on peut [lire en introduction du concept](http://www.vanschneider.com/work/mail/) par le concepteur derrière cette idée, que dis je , cet ensemble d’idée. Car pour revoir complètement l’email, le processus de réflexion passe par plusieurs points :

* Clean & cluster free interface
* Perfect spacing and clean typographie
* Only show what you really need
* Managing attachments from a dedicated view
* Social / Brand integration
* Actions Steps
Et c’est sans contexte ce dernier point qui est le plus génial. De nos jours, nous trions nos emails. Nous ne nous contentons pas de les lire, et bien souvent ce n’est pas notre première action lorsque l’on lance son client email. Nous faisons le tri entre les emails dont on peut se débarrasser de suite (newsletter, note de service, … tout ce qui ne nécessite pas un temps élevé pour assimiler l’information et/ou qui ne nécessite pas une réponse qu’on ne saurais formuler en moins de une minute) de ce qui nécessite une attention particulière, que nous n’avons pas nécessairement immédiatement.

De la même manière que des services comme [Instapaper](http://instapaper) , [Pocket (Read it later)](http://getpocket.com) ou encore la [liste de lecture de Safari](http://www.apple.com/osx/apps/#safari) pour mettre de coté une page web que l’on ne saurais analyser / traiter immédiatement, on ne sait pas en faire autant à l’heure actuelle, de manière simple et surtout , permettant de donner un ordre d’importance à ses derniers. Les *ActionSteps* sont là pour cela. Elles nous permettrons ainsi d’avoir une liste de mails a traiter, automatiquement rangé par priorité.

### Google Drive

![](/img/0*Z2mLteSYEjlEKtzD.png)#### [Archy](http://www.archyapp.com) *Mac osX*

Avec l’essor de *Google Drive*, il nous manquait quelques petits utilitaires pratiques qui nous faciliter la vie & le partage de ressource. C’est maintenant chose faite avec* *A*chy*.

Ce petit utilitaire va vous permettre de :

* Gérer facilement qui peut accéder à quoi, avec une interface conviviale
* Partager avec un simple drag’n’drop un document ou un dossier
* Utiliser votre bon vieux raccourcis Espace pour afficher un aperçu
* Editer avec n’importe quelle application de votre mac
* Avoir des notifications sur les éditions, nouveaux fichiers, upload de document …
Et bonne nouvelle, L’application est compatible Mountain Lion, utilise [Grand Central Dispatch](http://en.wikipedia.org/wiki/Grand_Central_Dispatch) et [Core Data](http://en.wikipedia.org/wiki/Core_Data) pour vous offrir des performances maximales. Et cerise sur le gâteau, il est *gratuit*.

### Mountain Lion

Personne n’a pus échapper à la sortie de Mountain Lion et sont lot de nouvelles fonctionnalités, de nouvelles contraintes et déjà d’utilisateurs mécontent. Rapide tour des problèmes & solutions que nous pouvons trouver sur internet

#### PowerNap

Power Nap est une nouvelle fonction proposé sous Mountain Lion qui est en fait basée sur une technologie déjà existante sous Snow Léopard qui tire partie des puces intel à faible consommation pour exécuter votre OS sans faire fonctionner ni l’écran ni les ventilateurs ni le GPU. Ici cela ne fonctionne qu’avec un SSD pour des raisons de consommation électrique et vous permet d’avoir un mac toujours a jour, puisque celle ci se font quand vous n’êtes pas sur votre machine. De même celle ci continue a recevoir email, photo, contact, mise a jour de calendrier, de notes, de rappels, fait sa sauvegarde TimeMachine et Fait ses mises a jour sur l’appStore. Ah oui il indexe le disque pour Spotlight et réponds a Find My Mac ou aux accès VPN . Pour plus d’information, Le journal du lapin nous gratifie d’un [article de description complet](http://www.journaldulapin.com/2012/07/27/power-nap-explications-precisions/) mais surtout d’une [astuce pour activer PowerNap sur les Macbook Air 2010](http://www.journaldulapin.com/2012/07/29/activer-power-nap-sur-les-macbook-air-2010/). En effet contrairement à ce qui avait été annoncé lors de la keynote, les macbook air 2010 ne sont pas supporté, seules les toutes dernières machines sont officiellement capable d’accéder à cette fonction.

#### Partage Web

Avec Mountain Lion, on voit disparaitre une fonctionnalité bien pratique pour les développeurs un peu fainéant qui ne souhaitent pas bosser avec une machine virtuelle : le partage web.

Derrière ce nom se cache en fait tout simplement un serveur apache activé à la volée et super optimisé pour le mac. Et vous savez quoi ? Il est toujours présent sur Mountain Lion, il n’y a juste plus d’interface utilisateur graphique pour le gérer. Qu’à cela ne tienne, voici [un petit prefPane](http://clickontyler.com/blog/2012/02/web-sharing-mountain-lion/) qui se charge de faire là même chose, et qui à pus être codé grâce au code openSourcé de [virtualhostx](http://clickontyler.com/virtualhostx/) logiciel de gestion de virtual host pour mac osX (pas trop mal au demeurant, 30j d’essai gratuit).

#### Centre de notification et Growl

Avant le centre de notification, il y avait Growl (qui était honteusement devenu payant avec l’arrivée du MacAppStore) qui permettais d’afficher des notifications sur votre bureau, avec pleins de styles différents, que n’importe qui maîtrisant HTML, CSS et Javascript pouvait éditer, créer, et ensuite partager avec tout l’Internet.

Mais voila le centre de notification est là et des applications ne sont pas encore prêtes pour envoyer leurs notifications dedans, et continue de les envoyer à Growl (qui fonctionne soit comme app résidente installé par l’utilisateur, soit comme add on de l’app disponible via un SDK). [Hiss](http://collect3.com.au/hiss/) va vous permettre de forwarder ses notifications de Growl vers le centre de notification en replaçant Growl. En gros Hiss se fait passer pour Growl, reçoit les notifications et les envois au Centre de Notification. Parfait pour une transition en douceur non ?

  
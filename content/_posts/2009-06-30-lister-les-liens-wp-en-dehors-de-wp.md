---
layout:	post
title:	"Lister les liens WP en dehors de WP"
date:	2009-06-30
---

  Il arrive que parfois on ai besoin de passer des requetes en dehors du moteur wordpress, et comme c’est mon cas aujourd’hui je vous livre le bout de code qui permet de lister les liens dans la blogroll sans passer par WP :

query("SELECT * FROM wp\_links;");// on passe la requete  
echo "* [“.$row[‘link\_name’].”](%22.$row[ "\".$row[")
";//on ferme  
$db->close();//on oublie aps de fermer l'acces a la bdd !  
?>Bien sur vous pouvez aussi télécharger le fichier php qui va bien ici : [WP\_LINK\_GRABBER](http://lageeknote.com/wp-content/uploads/2009/06/requete.php)

![](/img/0*32bPcUF9kkDDn0Q8.)  
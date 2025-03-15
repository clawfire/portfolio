---
layout: post
title: Comment Récupérer l'Accès Administrateur à un Site WordPress
description: |
  Découvrez comment récupérer l'accès administrateur à un site WordPress grâce à des méthodes simples et efficaces : réinitialisation via URL, ajout d'un administrateur avec PhpMyAdmin ou FTP, et assistance de l'hébergeur. Protégez votre site avec des conseils de sécurité essentiels. Un guide complet pour les utilisateurs WordPress.
date: 2025-03-15T22:48:11.197Z
featured_image: img/2025/03/Image HD Unsplash.jpg
published: true
tags:
  - Accès administrateur WordPress
  - FTP WordPress
  - Guide WordPress
  - Hébergement WordPress
  - PhpMyAdmin WordPress
  - Récupération mot de passe WordPress
  - Sauvegarde WordPress
  - Sécurité WordPress
  - WordPress
  - Problème connexion WordPress
categories: []
fmContentType: Blog Post
keywords:
  - WordPress
---

Perdre l'accès administrateur à son site WordPress peut être stressant, mais plusieurs solutions existent pour le récupérer. Que ce soit via l'interface, la base de données ou des outils comme FTP, voici les étapes détaillées pour résoudre ce problème.

## 1. Réinitialiser le mot de passe via l'URL

La première méthode, souvent la plus simple, consiste à réinitialiser le mot de passe depuis la page de connexion WordPress :

1. Rendez-vous sur la page de connexion : `https://votresite.fr/wp-admin/?action=lostpassword.`
2. Entrez votre adresse email associée au compte administrateur.
3. Suivez les instructions pour recevoir un lien de réinitialisation par email.

Cette méthode est rapide si vous avez encore accès à l'adresse email liée à votre compte. Mais bon, on ne va pas se voiler la face, si vous êtes ici à lire c'est que vous n'avez sans doute pas d'accès admin (genre on vous a piraté votre site et supprimé l'utilisateur).

## 2. Ajouter un nouvel administrateur via PhpMyAdmin

Si vous avez accès à la base de données de votre site via PhpMyAdmin, vous pouvez créer un nouvel utilisateur administrateur :

1. Connectez-vous à PhpMyAdmin depuis votre hébergeur.
2. Exécutez les requêtes SQL suivantes en remplaçant les valeurs par vos informations personnelles :

    ```sql
    INSERT INTO `wp_users`(`user_login`, `user_pass`, `user_nicename`, `user_email`, `user_status`)
    VALUES ('nouveau_login', MD5('nouveau_mot_de_passe'), 'nom', 'email@exemple.com', '0');

    INSERT INTO `wp_usermeta`(`umeta_id`, `user_id`, `meta_key`, `meta_value`)
    VALUES (NULL, (SELECT MAX(ID) FROM wp_users), 'wp_user_level', '10');

    INSERT INTO `wp_usermeta`(`umeta_id`, `user_id`, `meta_key`, `meta_value`)
    VALUES (NULL, (SELECT MAX(ID) FROM wp_users), 'wp_capabilities', 'a:1:{s:13:"administrator";s:1:"1";}');
    ```

3. Une fois les requêtes exécutées, connectez-vous avec les nouveaux identifiants.

## 3. Créer un administrateur via FTP

Si vous avez un accès FTP à votre site, cette méthode permet de créer un compte administrateur directement dans le code :

1. Accédez au fichier `functions.php` de votre thème actif via un client FTP.
2. Ajoutez le code suivant au fichier :
    ```php
    (\$_SERVER['REMOTE_ADDR'] === 'VOTRE_ADRESSE_IP' && isset($_GET['add_admin'])) {
        $username = 'nouveau_admin';
        $password = 'mot_de_passe';
        $email = 'email@example.com';
        if (!username_exists($username) && !email_exists($email)) {
            $user_id = wp_create_user($username, $password, $email);
            $user = new WP_User($user_id);
            $user->set_role('administrator');
            echo 'Compte administrateur créé avec succès.';
        } else {
            echo 'Le compte existe déjà.';
        }
        die();
    }
    ```
3. Accédez à l’URL suivante : `https://votresite.fr?add_admin=true.`

## 4. Contacter l’hébergeur

Si aucune des solutions précédentes ne fonctionne, il est temps de contacter votre hébergeur. Voici ce que vous pouvez faire :

* Demandez une restauration depuis une sauvegarde récente de votre site.
* Fournissez les informations nécessaires, comme votre nom de domaine et vos identifiants client.

## Conseils pour éviter ce problème à l’avenir

Une fois l'accès récupéré, il est essentiel de sécuriser votre site pour prévenir de futures pertes :

* **Utilisez des mots de passe forts :** Combinez lettres, chiffres et caractères spéciaux.
* **Activez l’authentification à deux facteurs (2FA) :** Cela ajoute une couche de sécurité supplémentaire.
* **Effectuez des sauvegardes régulières :** Utilisez des plugins comme UpdraftPlus ou des solutions d’hébergement intégrées.
* **Surveillez les accès :** Configurez des alertes pour détecter les connexions suspectes.

---

En suivant ces étapes, vous devriez pouvoir récupérer l'accès à votre site WordPress rapidement et efficacement. Si vous avez des questions ou besoin d’aide supplémentaire, n’hésitez pas à me contacter.

---
Photo de [Fikret tozak](https://unsplash.com/fr/@tozakfikret?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) sur [Unsplash](https://unsplash.com/fr/photos/moniteur-allume-rfNLa1HL7eY?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)

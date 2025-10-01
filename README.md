# MEMO

Application de réseau social minimaliste en PHP/MySQL.

## Fonctionnalités
- Authentification: inscription, connexion, déconnexion
- Profil: consultation du profil, changement de photo de profil
- Publications: création de posts, likes, commentaires
- Recherche: recherche d’utilisateurs
- Notifications basiques
- Gestion des amis (ajout)

## Prérequis
- PHP 8+ (extension `mysqli` activée)
- MySQL/MariaDB
- Serveur web local (MAMP/XAMPP) ou serveur interne PHP
- Navigateur moderne

## Installation
1) Cloner uniquement ce dossier du dépôt:
```bash
git clone https://github.com/aminehmt/MEMO-social-media.git
cd MEMO-social-media
```
2) Créer une base de données (par défaut `reseau_bdd`).
3) Configurer l’accès à la base dans `connexion_bdd.php`.

## Configuration de la base (`connexion_bdd.php`)
Modifiez les constantes de connexion selon votre environnement:
```php
<?php
$serveur = "localhost";
$utilisateur = "root";
$mot_de_passe = "";
$base_de_donnees = "reseau_bdd";

$db_connexion = new mysqli($serveur, $utilisateur, $mot_de_passe, $base_de_donnees);
if ($db_connexion->connect_error) {
    die("Erreur de connexion à la base de données : " . $db_connexion->connect_error);
}
?>
```

> Remarque: Importez votre schéma/données SQL dans la base (via phpMyAdmin ou CLI) avant d’utiliser l’application.

## Lancement en local
- Avec un stack local (MAMP/XAMPP): placez le dossier dans `htdocs` (ou équivalent) puis ouvrez `http://localhost/reseausocial/page_connexion.php`.
- Ou avec le serveur interne PHP depuis ce dossier:
```bash
php -S 127.0.0.1:8000
# Puis ouvrez http://127.0.0.1:8000/page_connexion.php
```

## Structure du dossier
- Pages PHP: `page_connexion.php`, `page_inscription.php`, `page_principale.php`, `page_profile.php`, `page_profile_visiteur.php`, `page_commentaire.php`, `page_resultat_recherche.php`, `page_notifications.php`
- Actions: `ajout_post.php`, `ajouter_ami.php`, `traitement_commentaire.php`, `traitement_like.php`
- Layout: `header.php`
- Connexion BDD: `connexion_bdd.php`
- Assets: images et icônes (`*.png`, `*.jpg`)

## Captures d’écran
Aperçu de quelques écrans (si non visibles, actualisez la page du dépôt):

![Logo](MEMOf.png)
![Exemple](Photo.png)

## Dépannage
- Page blanche: vérifiez les erreurs PHP (activer `display_errors` en dev) et la configuration BDD.
- Connexion impossible: validez l’hôte, l’utilisateur, le mot de passe et le nom de base dans `connexion_bdd.php`.
- Assets manquants: assurez-vous que le chemin des images est correct et accessible.

## Licence
Projet pédagogique. Utilisation libre pour apprentissage.

## Dépôt
`https://github.com/aminehmt/MEMO-social-media`

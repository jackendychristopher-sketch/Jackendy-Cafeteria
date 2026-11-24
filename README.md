
Cette application en Python permet de gérer le stock d'ingrédients, les produits et leurs recettes, les clients avec remises pour les étudiants et le personnel, le suivi des commandes, l'historique des actions et la sauvegarde des données dans un fichier JSON. Elle est prévue pour fonctionner sur Google Colab et en local sur macOS.
Classes principales
 * Client : classe de base avec identifiant, nom et calcul du montant total.
 * Etudiant : sous-classe de Client appliquant par défaut une remise de 15 %.
 * Personnel : sous-classe de Client appliquant par défaut une remise de 10 %.
 * Produit : représente un produit avec son identifiant, son nom, son prix et sa recette, et calcule les besoins selon la quantité demandée.
 * Commande : gère l'identifiant, le client, les articles, le statut (en_preparation, prete, livree, annulee) et le montant final.
 * Cafeteria : gère le stock, les produits, les clients, les commandes, l'historique, la recherche, le tri, les indicateurs et la sauvegarde JSON.
Règles principales
 * Stock atomique : tous les ingrédients nécessaires sont vérifiés avant de débiter le stock lors de la création d'une commande. S'il manque un ingrédient, aucune unité n'est retirée.
 * Annulation : une commande déjà livrée ou déjà annulée ne peut pas être annulée. L'annulation d'une commande remet les ingrédients dans le stock, met le statut à annulee et remet le montant final à 0.0.
 * Persistance JSON : les données sont enregistrées en UTF-8 dans donnees_cafeteria.json, avec gestion d'erreur si le fichier est absent ou invalide.
Fichiers du projet
 * cafeteria.py : code source principal et menu interactif en console.
 * demo_data.json : jeu de données d'exemple.
 * README.txt : documentation du projet en texte brut.
 * rapport_projet.pdf : rapport technique du projet.
Utilisation
 * Sur Mac (Terminal) : lancer python3 cafeteria.py dans le dossier du projet.
 * Sur Google Colab : exécuter le code de cafeteria.py et utiliser le menu interactif.

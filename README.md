# Apache + PHP + Docker Compose

Projet minimal affichant une phrase personnalisée dans `index.php` à partir de la variable `NOM` définie dans `.env`.

## Démarrage

1. Cloner le dépôt : `git clone <URL_DU_DEPOT>` puis `cd <DOSSIER_DU_DEPOT>`.
2. Copier le modèle : `cp .env.example .env` (sur PowerShell : `Copy-Item .env.example .env`).
3. Ouvrir `.env` et modifier `NOM=VotreNom`.
4. Exécuter `docker compose up -d --build`.
5. Accéder à http://localhost:8080.

Pour arrêter : `docker compose down`.

## Fonctionnement

Docker Compose charge le fichier `.env` pour remplacer `${NOM}` dans `compose.yaml`. La variable est transmise au conteneur en tant que variable d'environnement. PHP la lit via `getenv('NOM')`. Le fichier `.env` n'est **pas** copié dans l'image Docker et est exclu de Git. Adaptez le port `8080` si nécessaire.

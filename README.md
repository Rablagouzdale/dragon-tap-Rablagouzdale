# DragonTap
Dragon tap est une application web de gestion des commandes.

📦 Prérequis
Avant de lancer le projet, il faut :

Docker Desktop installé

Docker Compose v2 (inclus dans Docker Desktop)

⚠️ Problèmes rencontrés :
Éviter OneDrive sous Windows pour éviter les problèmes de permissions et de lecture de fichiers YAML
Les conflits de noms de conteneurs
La typo


📱 Lancer l’application
Une seule commande pour tout lancer :
docker compose up -d --build

Cette commande :

construit les images Docker

crée le réseau dragontap-net

crée le volume cellar-data

exécute le script cellar/init.sql si le volume est vide

démarre les services dans le bon ordre (cellar → innkeeper → board)

    cellar base de données en PostGreSQL

    innkeeper c'est l'API backend

    board c'est le frontend Nginx    

🌐 URLs

Service	URL	Description
API (innkeeper)	http://localhost:4181/api/health	Vérifie que l’API tourne et que la DB est connectée
Frontend (board)	http://localhost:4182	Interface utilisateur


🛑 Arrêter l’application

Arrêter les conteneurs :
docker compose down


Tout supprimer (conteneurs + réseau + volume) :
docker compose down -v

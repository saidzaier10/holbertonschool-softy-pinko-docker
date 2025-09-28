# 🐳 Holberton School - Softy Pinko Docker Project

## 📋 Description

Ce projet consiste à créer une infrastructure complète d'application web conteneurisée avec Docker. L'architecture finale comprend un reverse proxy, un load balancer, plusieurs serveurs d'API et un serveur de contenu statique front-end.

## 🏗️ Architecture

```
Client → Proxy Server (Nginx) → ├── Front-end Server (Nginx)
                                └── API Servers (Flask) [Load Balanced]
```

- **Proxy Server** : Point d'entrée unique qui route le trafic
- **Front-end Server** : Sert le contenu statique HTML/CSS/JS
- **API Servers** : Serveurs Flask fournissant des données dynamiques
- **Load Balancer** : Distribution Round Robin entre les serveurs API

## 📁 Structure du Projet

```
holbertonschool-softy-pinko-docker/
├── task0/          # Image Docker basique Ubuntu
├── task1/          # Serveur Flask simple
├── task2/          # Serveur front-end Nginx + back-end Flask
├── task3/          # Communication front-end/back-end avec CORS
├── task4/          # Docker Compose pour orchestration
├── task5/          # Ajout du serveur proxy
└── task6/          # Mise à l'échelle horizontale
```

## 🛠️ Prérequis

- Docker Desktop installé
- Connaissance de base de Docker et Docker Compose
- Port 80 disponible sur votre machine

## 🚀 Installation et Utilisation

### Task 0 - Image Docker de base
```bash
cd task0
docker build -f ./Dockerfile -t softy-pinko:task0 .
docker run -it --rm --name softy-pinko-task0 softy-pinko:task0
```

### Task 1 - API Flask
```bash
cd task1
docker build -f ./Dockerfile -t softy-pinko:task1 .
docker run -p 5252:5252 -it --rm --name softy-pinko-task1 softy-pinko:task1
```

### Task 2 - Front-end et Back-end séparés
```bash
cd task2
# Back-end
docker build -f ./back-end/Dockerfile -t softy-pinko-back-end:task2 ./back-end
# Front-end
docker build -f ./front-end/Dockerfile -t softy-pinko-front-end:task2 ./front-end
```

### Task 3 - Communication Front/Back avec CORS
```bash
cd task3
# Lancer le back-end dans un terminal
docker run -p 5252:5252 -it --rm --name softy-pinko-back-end-task3 softy-pinko-back-end:task3
# Lancer le front-end dans un autre terminal
docker run -p 9000:9000 -it --rm --name softy-pinko-front-end-task3 softy-pinko-front-end:task3
```

### Task 4 - Docker Compose
```bash
cd task4
docker-compose build
docker-compose up
```

### Task 5 - Serveur Proxy
```bash
cd task5
docker-compose build
docker-compose up
```
Accédez à l'application sur http://localhost

### Task 6 - Mise à l'échelle
```bash
cd task6
docker-compose build
# Lancer avec plusieurs instances du back-end
docker-compose up --scale back-end=2
```

## 🔧 Technologies Utilisées

- **Docker** : Conteneurisation
- **Docker Compose** : Orchestration multi-conteneurs
- **Nginx** : Serveur web et reverse proxy
- **Flask** : Framework Python pour l'API
- **Flask-CORS** : Gestion des requêtes cross-origin
- **HTML/CSS/JavaScript** : Interface front-end

## 📝 Concepts Clés

### Reverse Proxy
- Route le trafic vers les services appropriés
- Cache les serveurs internes du client
- Centralise les points d'entrée

### Load Balancing
- Algorithme Round Robin
- Distribution équitable des requêtes
- Scalabilité horizontale

### Conteneurisation
- Isolation des environnements
- Portabilité des applications
- Déploiement simplifié

## 🎯 Objectifs d'Apprentissage

- ✅ Créer et configurer des images Docker
- ✅ Utiliser Docker Compose pour l'orchestration
- ✅ Implémenter un reverse proxy avec Nginx
- ✅ Configurer un load balancer
- ✅ Gérer la communication entre conteneurs
- ✅ Mettre à l'échelle horizontalement des services

## 📚 Ressources Utiles

- [Documentation Docker](https://docs.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Nginx Documentation](https://nginx.org/en/docs/)
- [Flask Documentation](https://flask.palletsprojects.com/)

## 👥 Auteur

Projet réalisé dans le cadre du cursus Holberton School

---

*Note : Assurez-vous que Docker Desktop est en cours d'exécution avant de lancer les commandes.*
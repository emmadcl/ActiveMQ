# ActiveMQ

# ActiveMQ avec Docker

## Introduction
Ce projet propose une méthode simple pour lancer et gérer des serveurs ActiveMQ avec Docker. En utilisant Docker et Docker Compose, vous pouvez rapidement mettre en place un serveur ActiveMQ dans différentes versions, adapté aux besoins de vos environnements de développement et de test.

---

## Prérequis

- **Docker** : [Installation Docker](https://docs.docker.com/get-docker/)
- **Docker Compose** : [Installation Docker Compose](https://docs.docker.com/compose/install/)

---

## Lancer ActiveMQ avec Docker

Ce guide décrit les étapes nécessaires pour lancer ActiveMQ dans un conteneur Docker à l’aide de Docker Compose. Vous trouverez les principales commandes pour démarrer et vérifier l'état du serveur ActiveMQ, ainsi que les méthodes de diagnostic de l'adresse IP et des ports utilisés.

### Étape 1 : Démarrer ActiveMQ

Utilisez Docker Compose pour lancer le serveur ActiveMQ en arrière-plan.

```bash
docker-compose up -d
```

Cette commande démarre le conteneur ActiveMQ en utilisant le fichier `docker-compose.yml` qui contient toutes les configurations nécessaires.

### Étape 2 : Vérifier les conteneurs en cours d'exécution

Pour vérifier que le conteneur ActiveMQ est actif :

```bash
docker container ls
```

Cette commande liste tous les conteneurs en cours d'exécution, affichant des informations comme l’ID du conteneur, l’image utilisée, son état actuel, et les ports exposés.

---

## Scan de l'adresse IP et des ports d'ActiveMQ

Pour effectuer un scan et obtenir les détails sur les ports utilisés par ActiveMQ, suivez ces étapes :

### Étape 1 : Trouver l'adresse IP

Pour identifier l'interface réseau active et l'adresse IP associée :

```bash
ip a
```

Cette commande liste toutes les interfaces réseau, permettant de voir l'adresse IP associée à l’interface active.

### Étape 2 : Scanner les ports d'ActiveMQ

Avec l'adresse IP obtenue, utilisez `nmap` pour scanner tous les ports ouverts :

```bash
nmap -p- [adresse_ip]
```

Cette commande identifie tous les ports ouverts par le serveur ActiveMQ.

---

## Versions disponibles

Ce projet prend en charge plusieurs versions d’ActiveMQ. Vous pouvez ajuster le fichier `docker-compose.yml` pour spécifier la version souhaitée :

- ActiveMQ_2015
- ActiveMQ_2016
- ActiveMQ_2022
- ActiveMQ_2023

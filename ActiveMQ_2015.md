## ActiveMQ_2015

### Scan du Réseau
Pour ActiveMQ_2015, l'adresse IP assignée est `172.18.0.1`. Voici une capture d'écran illustrant le scan du réseau :

![activemq_1](https://github.com/user-attachments/assets/c065290b-f0b6-494e-bffa-7eb4c21eb14f)

Grâce à ce scan, nous avons identifié que le port d'intérêt pour accéder à l'interface est le **8161**. Pour accéder à la console web, utilisez le lien suivant : [http://localhost:8161](http://localhost:8161).

### Version d'ActiveMQ
Pour déterminer la version d'ActiveMQ, connectez-vous à la console d'administration avec les informations d'identification par défaut :

- **Login** : `admin`
- **Mot de passe** : `admin`

![activemq2015_2](https://github.com/user-attachments/assets/607d12b4-daab-400b-aa08-24301374fab4)

### CVE Score
La vulnérabilité **CVE-2015-5254** est associée à cette version d'ActiveMQ.

![activemq_2015_cve](https://github.com/user-attachments/assets/95f3fe86-f8c9-47de-ab49-00ba819c6e24)

Cette vulnérabilité est liée à une faille de sécurité dans la console web d'administration d'Apache ActiveMQ. Elle permet à un attaquant non authentifié d'exécuter du code à distance en exploitant une mauvaise gestion des permissions, ce qui peut conduire à une compromission du système.

## Stratégie de Compromission

[Stratégie de compromission](compromission2015.rb)

### Exploitation/Explication

#### 1. Objectif du Module
Ce module permet de téléverser un fichier JSP malveillant en contournant les restrictions de chemin via une technique `..//`. Il permet également d'obtenir un accès shell à distance.

#### 2. Fonctionnement
1. Utilisation des identifiants par défaut (**admin:admin**).
2. Vérification de la vulnérabilité de la cible.
3. Téléversement du payload JSP puis exécution de ce dernier.
4. Accès obtenu au shell.

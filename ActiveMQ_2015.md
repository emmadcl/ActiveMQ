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
La vulnérabilité **CVE-2015-51830** est associée à cette version d'ActiveMQ.

![Capture d’écran 2024-11-01 175751](https://github.com/user-attachments/assets/581dda2f-d540-4f85-8a0b-8f15842c2fc6)

Cette vulnérabilité est lié à une mauvaise gestion des autorisations dans la console web d'administration d'Apache ActiveMQ. En particulier, les utilisateurs non autorisés pourraient potentiellement accéder à des informations sensibles ou exécuter certaines actions de gestion sans authentification adéquate.

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

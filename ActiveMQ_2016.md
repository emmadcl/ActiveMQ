## ActiveMQ_2016

### Scan du Réseau
Pour ActiveMQ_2016, l'adresse IP assignée est `172.19.0.1`. Voici une capture d'écran illustrant le scan du réseau :

![activemq_1](https://github.com/user-attachments/assets/c065290b-f0b6-494e-bffa-7eb4c21eb14f)

Grâce à ce scan, nous avons identifié que le port d'intérêt pour accéder à l'interface est le **8161**. Pour accéder à la console web, utilisez le lien suivant : [http://localhost:8161](http://localhost:8161).

### Version d'ActiveMQ
Pour déterminer la version d'ActiveMQ, connectez-vous à la console d'administration avec les informations d'identification par défaut :

- **Login** : `admin`
- **Mot de passe** : `admin`

![activemq2015_2](https://github.com/user-attachments/assets/607d12b4-daab-400b-aa08-24301374fab4)

### CVE Score
La vulnérabilité **CVE-2016-6810** est associée à cette version d'ActiveMQ.



## Stratégie de Compromission
Cette section détaille la stratégie de compromission pour exploiter cette vulnérabilité.

---

### Exploitation/Explication

#### 1. Objectif du Module
Ce module permet de téléverser un fichier JSP malveillant en contournant les restrictions de chemin via une technique `..//`. Il permet également d'obtenir un accès shell à distance.

#### 2. Fonctionnement
1. Utilisation des identifiants par défaut (**admin:admin**).
2. Vérification de la vulnérabilité de la cible.
3. Téléversement du payload JSP puis exécution de ce dernier.
4. Accès obtenu au shell.

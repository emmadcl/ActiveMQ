
## ActiveMQ_2022

### Scan du Réseau
Pour ActiveMQ_2022, l'adresse IP assignée est `172.20.0.1`. Voici une capture d'écran illustrant le scan du réseau :

![activemq_2022_1](https://github.com/user-attachments/assets/a7c26cf8-400a-4de5-b1bc-28e7cf831fd0)

Grâce à ce scan, nous avons identifié que le port d'intérêt pour accéder à l'interface est le **8161**. Pour accéder à la console web, utilisez le lien suivant : [http://localhost:8161](http://localhost:8161).

### Version d'ActiveMQ
Pour déterminer la version d'ActiveMQ, connectez-vous à la console d'administration avec les informations d'identification par défaut :

- **Login** : `admin`
- **Mot de passe** : `admin`

![activemq_2022_2](https://github.com/user-attachments/assets/44b384b2-39e7-4358-87ac-da09c1a533a0)

### CVE Score
La vulnérabilité **CVE-2022-41678** est associée à cette version d'ActiveMQ.

![activemq_2022_cve](https://github.com/user-attachments/assets/d5081ce1-c131-4017-86c8-a1038e8e097d)

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

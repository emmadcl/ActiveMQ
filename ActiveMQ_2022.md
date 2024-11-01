
## ActiveMQ_2022

### Scan du Réseau
Pour ActiveMQ_2022, l'adresse IP assignée est `172.20.0.1`. Voici une capture d'écran illustrant le scan du réseau :

![activemq_2016_1](https://github.com/user-attachments/assets/50652424-34fc-400d-846c-2e081c43d7e2)

Grâce à ce scan, nous avons identifié que le port d'intérêt pour accéder à l'interface est le **8161**. Pour accéder à la console web, utilisez le lien suivant : [http://localhost:8161](http://localhost:8161).

### Version d'ActiveMQ
Pour déterminer la version d'ActiveMQ, connectez-vous à la console d'administration avec les informations d'identification par défaut :

- **Login** : `admin`
- **Mot de passe** : `admin`

![activemq_2016_2](https://github.com/user-attachments/assets/048ea9fe-1028-4452-be71-403caf4607a1)

### CVE Score
La vulnérabilité **CVE-2022-41678** est associée à cette version d'ActiveMQ.

![activemq_2016_cve](https://github.com/user-attachments/assets/5190b795-3ea1-4e08-ad1c-c3750cdf5080)

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

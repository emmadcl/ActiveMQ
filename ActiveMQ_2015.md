## ActiveMQ_2015

### Scan du Réseau
Pour ActiveMQ_2015, l'adresse IP assignée est `172.18.0.1`. Voici une capture d'écran illustrant le scan du réseau :

![Capture d'écran Scan Réseau](./activemq_1.jpg)

Grâce à ce scan, nous avons identifié que le port d'intérêt pour accéder à l'interface est le **8161**. Pour accéder à la console web, utilisez le lien suivant : [http://localhost:8161](http://localhost:8161).

### Version d'ActiveMQ
Pour déterminer la version d'ActiveMQ, connectez-vous à la console d'administration avec les informations d'identification par défaut :

- **Login** : `admin`
- **Mot de passe** : `admin`

![Capture d'écran Version ActiveMQ](./activemq2015_2.jpg)

### CVE Score
La vulnérabilité **CVE-2015-5254** est associée à cette version d'ActiveMQ.

![Capture d'écran CVE Score](./activemq_2015_cve.jpg)

Cette vulnérabilité est liée à une faille de sécurité dans la console web d'administration d'Apache ActiveMQ. Elle permet à un attaquant non authentifié d'exécuter du code à distance en exploitant une mauvaise gestion des permissions, ce qui peut conduire à une compromission du système.

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

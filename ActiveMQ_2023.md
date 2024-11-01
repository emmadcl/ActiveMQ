
## ActiveMQ_2023

### Scan du Réseau
Pour ActiveMQ_2023, l'adresse IP assignée est `172.21.0.1`. Voici une capture d'écran illustrant le scan du réseau :

![activemq_2023_1](https://github.com/user-attachments/assets/0eb90016-ac2b-4920-b0f2-61c5d08576a2)

Grâce à ce scan, nous avons identifié que le port d'intérêt pour accéder à l'interface est le **8161**. Pour accéder à la console web, utilisez le lien suivant : [http://localhost:8161](http://localhost:8161).

### Version d'ActiveMQ
Pour déterminer la version d'ActiveMQ, connectez-vous à la console d'administration avec les informations d'identification par défaut :

- **Login** : `admin`
- **Mot de passe** : `admin`

![activemq_2023_2](https://github.com/user-attachments/assets/9e77e2fb-be08-46e1-84db-08ac8387d226)

### CVE Score
La vulnérabilité **CVE-2023-46604** est associée à cette version d'ActiveMQ.

![activemq_2023_cve](https://github.com/user-attachments/assets/d7a87a84-a605-4370-84e1-c7bf30a4d1b2)

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

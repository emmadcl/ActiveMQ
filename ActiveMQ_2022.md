
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

[Stratégie de compromission](compromission2022.py)

## Exploitation/Explication

### 1. Objectif du Module
Le module d'exploitation vise à tirer parti de la vulnérabilité **CVE-2022-41678** présente dans Apache ActiveMQ. Cette vulnérabilité est due à une désérialisation de données non fiables, permettant à un attaquant de téléverser un fichier JSP malveillant ou de modifier la configuration du serveur pour exécuter du code arbitraire à distance. L'exploitation de cette faille peut donner accès à un shell distant sur le serveur.

### 2. Fonctionnement

1. **Initialisation de la Session** :
   - Le script initie une session HTTP avec les informations d'identification par défaut de la console ActiveMQ (`admin:admin`), et se prépare à exécuter les actions exploitant la vulnérabilité.

2. **Identification du MBean** :
   - Le module recherche les MBeans pertinents sur le serveur via l'API Jolokia. Il cible le MBean `org.apache.logging.log4j2` ou `jdk.management.jfr` (Java Flight Recorder) pour manipuler la configuration du journal de log ou le système de gestion d'enregistrement, permettant ainsi l'injection du code malveillant.

3. **Injection du Payload JSP** :
   - En fonction du MBean identifié, le script injecte un payload dans la configuration du journal (`log4j`) ou dans la configuration de l’enregistrement (`jfr`).
   - Le payload injecté crée un fichier `shell.jsp` dans le répertoire d'administration (`/admin/shell.jsp`), permettant une exécution de commande à distance via une requête HTTP.

4. **Modification et Restauration de la Configuration** :
   - Après l'injection, le script restaure la configuration d'origine du journal ou du système de gestion d'enregistrement pour éviter une détection immédiate.

5. **Execution du Payload** :
   - Une fois le shell JSP créé, il est accessible à distance via l'URL `http://localhost:8161/admin/shell.jsp?cmd=id`.
   - En passant une commande en tant que paramètre `cmd`, un attaquant peut exécuter des commandes système sur le serveur ActiveMQ compromis.

### Exemple de Commande

Le module peut être exécuté en utilisant Python avec les paramètres suivants :

```bash
python3 exploit.py -u admin -p admin http://localhost:8161
```

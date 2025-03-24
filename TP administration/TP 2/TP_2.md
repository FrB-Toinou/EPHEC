# TP2 : Suite de la découverte de Docker
pas à jour
Noms des auteurs :  Brazier Antoine
Date de réalisation : 2025/02/17

## 1. Les volumes Docker

Documentez les commandes importantes de cette section. 

Quelles sont les différences entre les deux types de volumes utilisés ici ?  Dans quel cas utiliser l'un plutôt que l'autre? 


<source src="/TP administration/images/TP_2_du_1_2_image_1.png" type="screenshoot">

<source src="/TP administration/images/TP_2_du_1_2_image_2.png" type="screenshoot">

<source src="/TP administration/images/TP_2_du_1_2_image_3.png" type="screenshoot">

Bind Mount lie directement un dossier local, alors qu’un Volume Docker est géré par Docker et reste même après la suppression l'un des deux contenenaire.

Bind Mount : pour le développement (modifications en direct).
Volume Docker : pour le stockage partager et le stockage reste tant qu'il y a un conteneur de "connecter".

## 2. Les réseaux Docker

Documentez les commandes importantes de cette section. 
### 2.1. Réseau par défaut

1.  Quelles sont les interfaces réseau et adresses IP de chaque container? Vous pouvez trouvez cette information soit depuis l'hôte avec un ```docker inspect```(cfr TP1), soit depuis le container lui-même.  Note dans ce dernier cas : Si la commande ```ip addr```n'est pas disponible, installez le package ```iproute2```. 
web-volume : 
    - "IPAddress": "172.17.0.4"
<source src="/TP administration/images/TP_2_du_2_1_image_2.png" type="screenshoot">
web-volume-80: 
    - "IPAddress": "172.17.0.5",
    
<source src="/TP administration/images/TP_2_du_2_1_image_1.png" type="screenshoot">

2. Les containers peuvent-ils se joindre via ```ping``` ? 
Oui,
<source src="/TP administration/images/TP_2_du_2_1_image_3.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_2_1_image_4.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_2_1_image_5.png" type="screenshoot">

3. Les containers ont-ils accès à Internet ? 
Oui,
<source src="/TP administration/images/TP_2_du_2_1_image_6.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_2_1_image_7.png" type="screenshoot">

4. Est-ce une bonne idée d'utiliser ce réseau par défaut?  Quels en sont les avantages et les inconvénients ?  

### 2.2. Réseaux définis par l'utilisateur 

1. Le nouveau container ajouté sur le réseau ```my-net``` peut-il contacter les deux précédents (liés au réseau bridge par défaut)?  A-t-il accès à Internet?
Non, car il ne peut pas contacter les deux autres contenaires car ils ne sont pas dans le meme réseau.
Cependant,
<source src="/TP administration/images/TP_2_du_2_2_image_1.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_2_2_image_2.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_2_2_image_3.png" type="screenshoot">


2. Quels sont les différences entre ce nouveau réseau et le bridge par défaut?  Quels en sont les avantages et inconvénients ? 
screen : sur docker network inspect 
<source src="/TP administration/images/TP_2_du_2_2_image_4.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_2_2_image_5.png" type="screenshoot">


## 3. Docker-compose

1. Qu'avez-vous observé lors de cette première expérience avec Docker Compose ?  Faites un court bilan sur base de screenshots. 

<source src="3/docker-compose.yml" type="file">

<source src="/TP administration/images/TP_2_du_3_image_1.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_3_image_2.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_3_image_3.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_3_image_4.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_3_image_5.png" type="screenshoot">

2. Documentez les commandes importantes. 

docker compose up

docker inspect [container | network]

ping [IP | name]

docker compose down

## 4. Exercices récapitulatifs

### 4.1. Mise en application simple

 Votre infrastructure est-elle conforme à ce qui était attendu?  Comment avez-vous pu la valider?  Donnez les commandes utilisées et illustrez le résultat par des screenshots. 
<source src="/TP administration/images/TP_2_du_4_1_image_1.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_2.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_3.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_4.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_5.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_6.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_7.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_8.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_9.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_10.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_1_image_11.png" type="screenshoot">
### 4.2. Exemple du cours théorique

1. Dans cette infrastructure, comment les données sont-elles partagées?  Via des Bind Mounts ou des Volumes?  Pourquoi ? 

le web et la db sont sur le même réseau donc ils peuvent communiquer entre eux. de plus dans la zone docker possède un volume. néanmoins l'hote peut voir accès via bind mounts du dossier src et /app.


2. Quels sont les spécificités de chaque container? 
Le container WEB a pour rôle d'hébergé une application web, et le container DB a pour rôle de gérer la base de données MySQL.

3. Une fois démarrée, l'infrastructure est-elle conforme à ce qui était attendu?  Comment avez-vous pu la valider?  Donnez les commandes utilisées et illustrez le résultat par des screenshots. 
<source src="/TP administration/images/TP_2_du_4_2_image_1.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_2_image_2.png" type="screenshoot">
<source src="/TP administration/images/TP_2_du_4_2_image_3.png" type="screenshoot">

### 4.3. Exemple du tutoriel Docker

1. Quelles sont vos observations suite à la réalisation de ce tutoriel ? 
J'ai observer qu'on peut lancer n'importent quel type d'application via aux les containers.

2. Sur quelle base les containers sont-ils lancés ? 
Les containers sont lancés sur une base Python. et Redis.

3. Qu'avez-vous appris de nouveau ? 
On peut découper le fichier compose.yaml et en plusierus fichiers tels que des programmations en utilisant le mot "include" pour appeler le fichier.
develop watch :  permet de faire des modifications sans avoir besoin de relancer le container.
# TP2 : Suite de la découverte de Docker
pas à jour
Noms des auteurs :  ....................................
Date de réalisation : ....................................

## 1. Les volumes Docker

Documentez les commandes importantes de cette section. 

Quelles sont les différences entre les deux types de volumes utilisés ici ?  Dans quel cas utiliser l'un plutôt que l'autre? 

## 2. Les réseaux Docker

Documentez les commandes importantes de cette section. 
### 2.1. Réseau par défaut

1.  Quelles sont les interfaces réseau et adresses IP de chaque container? Vous pouvez trouvez cette information soit depuis l'hôte avec un ```docker inspect```(cfr TP1), soit depuis le container lui-même.  Note dans ce dernier cas : Si la commande ```ip addr```n'est pas disponible, installez le package ```iproute2```. 
2. Les containers peuvent-ils se joindre via ```ping``` ? 
3. Les containers ont-ils accès à Internet ? 
4. Est-ce une bonne idée d'utiliser ce réseau par défaut?  Quels en sont les avantages et les inconvénients ?  

### 2.2. Réseaux définis par l'utilisateur 

1. Le nouveau container ajouté sur le réseau ```my-net``` peut-il contacter les deux précédents (liés au réseau bridge par défaut)?  A-t-il accès à Internet?
2. Quels sont les différences entre ce nouveau réseau et le bridge par défaut?  Quels en sont les avantages et inconvénients ? 

## 3. Docker-compose

1. Qu'avez-vous observé lors de cette première expérience avec Docker Compose ?  Faites un court bilan sur base de screenshots. 
2. Documentez les commandes importantes. 

## 4. Exercices récapitulatifs

### 4.1. Mise en application simple

 Votre infrastructure est-elle conforme à ce qui était attendu?  Comment avez-vous pu la valider?  Donnez les commandes utilisées et illustrez le résultat par des screenshots. 

### 4.2. Exemple du cours théorique

1. Dans cette infrastructure, comment les données sont-elles partagées?  Via des Bind Mounts ou des Volumes?  Pourquoi ? 
2. Quels sont les spécificités de chaque container? 
3. Une fois démarrée, l'infrastructure est-elle conforme à ce qui était attendu?  Comment avez-vous pu la valider?  Donnez les commandes utilisées et illustrez le résultat par des screenshots. 


### 4.3. Exemple du tutoriel Docker

1. Quelles sont vos observations suite à la réalisation de ce tutoriel ? 
2. Sur quelle base les containers sont-ils lancés ? 
3. Qu'avez-vous appris de nouveau ? 


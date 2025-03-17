# TP1 : La découverte de Docker
Noms des auteurs :  Antoine Brazier
Date de réalisation : 2025/02/10


## 1. Premier container

### 1.1. Hello World 

Pouvez-vous expliquer avec vos mots ce qui s'est passé suite à l'exécution de cette commande?  
Après d'avoir entrer la commande "docker run hello-world" l'image de hello-world c'est lancé et à affichier ce texte dans la console : 
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/


### 1.2.  Observer un container


Retrouvez les informations suivantes sur le container lancé précédemment "commande : docker container ls -a" : 

1. Quel est son identifiant ? 99f56f84cb29    
2. Quel est son nom ? condescending_gol
3. Quel est son état ? condescending_gol
4. Quel est le nom de son image?  Avez-vous vu au point 1.1. d''où cette image provenait?  hello-world:latest
5. Quelle commande le container a-t-il exécuté? ? docker container list,
6. Si vous avez installer Docker Desktop, pouvez-vous retrouver ces mêmes informations dans l'interface graphique? 
<source src="/TP administration/images/TP_1_du_1_2_image_1.png>" type="screenshoot">

### 1.3. Les images 

1. Quelles informations voyez-vous? 
Les informations sont les suivantes REPOSITORY, TAG, IMAGE ID, CREATED et SIZE.

Quel est le lien avec ce que vous avez observé auparavant? 
Le lien est "Hello world".

<source src="/TP administration/images/TP_1_du_1_3_image_2.png" type="screenshoot">

2. Comparez l'output de cette commande avec la vue correspondante de l'interface graphique.  
<source src="/TP administration/images/TP_1_du_1_3_image_1.png" type="screenshoot">


3. Essayez de trouver la commande qui vous permettra de supprimer cette image.  C'est une bonne idée de ne pas conserver les images non utilisées sur votre système de fichiers : même avec la mutualisation de couches, elles prennent de l'espace sur le disque! 
La commande qui permet de supprimer des images est "docker rmi hello-world:latest".

## 2. Utiliser un container

### 2.1. Interagir avec un container

1. A quoi servent les options ```i``` et ```t```dans la commande ci-dessus?

I : --interactive                      Keep STDIN open even if not attached
T : -t, --tty                              Allocate a pseudo-TTY

Le ```i``` correspond à "interactive"   

2. Chaque container Docker est destiné à exécuter une commande unique.  Quelle est-elle dans ce cas-ci? 

Dans le terminal bash ouvrir l’image d’ubuntu si installer sinon l’installer sur la machine 

3. Dans le container, quels sont les processus présents?  Et leurs PIDs? 
Le pid est bash.
<source src="/TP administration/images/TP_1_du_2_1_image_1.png" type="screenshoot">

4. Avec quel utilisateur êtes-vous loggé? 

Je suis loggé avec l'utilisateur "root"

5. Votre container a-t'il accès à Internet?  Qui est son résolveur? 
Oui mon container a accès à Internet et son résolveur est le DNS.

### 2.2. Inspecter un container


1. Chaque container dispose d'une interface réseau.  Quelle est l'adresse **IP** de l'interface de votre container? 
<source src="/TP administration/images/TP_1_du_2_2_image_1.png" type="screenshoot">

2.  Votre container a-t'il des **ports** ouverts?  
Le container n'a aucun port ouvert.
<source src="/TP administration/images/TP_1_du_2_2_image_2.png" type="screenshoot">

### 2.3. Faire tourner un service dans un container



- Qu'avez-vous observé au niveau des "ports" ?  Expliquez et illustrez votre réponse avec des screenshots. 

Documentez ici la réalisation des exercices, via des explications et des snapshots. 
En utilisant la commande, On peut observer que le port n’est pas défini. Par conséquent l’image n’est pas accessibles en dehors de la machine

<source src="/TP administration/images/TP_1_du_2_3_image_1.png" type="screenshoot">

En utilisant la commande, On peut observer que le port n’est pas défini. Par conséquent l’image n’est pas accessibles en dehors de la machine.

<source src="/TP administration/images/TP_1_du_2_3_image_2.png" type="screenshoot">

## 3. Construire des images

### 3.1. Figer un container 
<source src="/TP administration/images/TP_1_du_3_1_image_1.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_3_1_image_2.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_3_1_image_3.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_3_1_image_4.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_3_1_image_5.png" type="screenshoot">

### 3.2. Créer une image sur base d'un Dockerfile

<source src="/TP administration/images/TP_1_du_3_2_image_1.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_3_2_image_2.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_3_2_image_3.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_3_2_image_4.png" type="screenshoot">

## Exercices récapitulatifs


### 4.1. Démarrer un serveur Web Apache
<source src="/TP administration/images/TP_1_du_4_1_image_1.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_4_1_image_2.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_4_1_image_3.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_4_1_image_4.png" type="screenshoot">

### 4.2. Lancer un résolveur Bind dans un container Docker

1. Quelle configuration avez-vous effectuée au niveau des ports ? 
<source src="/TP administration/images/TP_1_du_4_2_image_1.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_4_2_image_2.png" type="screenshoot">


2. Qu'avez-vous observé dans la trace Wireshark qui prouve que la configuration est correcte?  Illustrez avec un screenshot de la capture. 
<source src="/TP administration/images/TP_1_du_4_2_image_3.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_4_2_image_4.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_4_2_image_5.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_4_2_image_6.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_4_2_image_7.png" type="screenshoot">

### 4.3. Container avec script Python

<source src="/TP administration/images/TP_1_du_4_3_image_1.png" type="screenshoot">

<source src="/TP administration/images/TP_1_du_4_3_image_2.png" type="screenshoot">
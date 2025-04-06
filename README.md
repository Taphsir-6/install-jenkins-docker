# Installer Jenkins en utilisant Docker Compose

Ce dépôt contient une configuration Docker Compose pour une installation rapide de Jenkins. Cette configuration n'est pas destinée aux systèmes de production.

Références : Cette approche est principalement basée sur les [instructions officielles] (https://www.jenkins.io/doc/book/installing/docker/) mais profite de Docker Compose (en utilisant un fichier `docker-compose.yml`) pour réduire le nombre d'étapes nécessaires à l'installation et au fonctionnement de Jenkins.

# Installation de Docker

## Étape 1

Installez Docker localement (l'utilisation de Docker Desktop est probablement l'approche la plus simple).

## Étape 2

Cloner ce dépôt ou télécharger son contenu.

## Étape 3

Ouvrez une fenêtre de terminal dans le même répertoire que celui où se trouve le `Dockerfile` de ce dépôt. Construisez l'image Docker de Jenkins :

```
docker build -t my-jenkins .
```

## Étape 4

Démarrer Jenkins :

```
docker compose up -d
```

## Étape 5

Ouvrez Jenkins en allant sur : [http://localhost:8080/](http://localhost:8080/) et terminez le processus d'installation.

## Étape 6

Si vous souhaitez arrêter Jenkins et y revenir plus tard, exécutez :

```
docker compose down
```

Si vous souhaitez redémarrer Jenkins plus tard, exécutez simplement la même commande que celle de l'étape 3.


# Supprimer Jenkins

Une fois que vous avez fini de jouer avec Jenkins, il est peut-être temps de faire le ménage.

Exécutez la commande suivante pour mettre fin à Jenkins et pour supprimer tous les volumes et images utilisés :

```
docker compose down --volumes --rmi all
```

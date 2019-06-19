# Docker container

## Commandes de base

## Run

La commande run permet de démarrer un container d'exécution depuis une image.

Exemple avec [nextcloud](https://hub.docker.com/_/nextcloud/) :

```sh
docker run -d -p 8000:80 --name mycloud nextcloud
```

- **-d** lance l'application en arrière plan
- **-p** permet de publier le port de l'application
- **--name** option permettant de donner un nom au container
- **nextcloud** est le nom de l'image utilisé pour démarrer l'application


### Lancer un container en mode interactif

Télécharger l'image alpine :

```sh
docker pull alpine
```

puis :

```sh
docker run -it alpine sh
```


## Lister les containers

La sous commande **ps** permet d'afficher les containers (processus) en cour d'éxécution.

```sh
docker ps
```

L'option **-a** permet d'afficher les containers lancer mais stoppé.

```sh
docker ps -a
```

## Inspect

```sh
docker inspect -f "{{ .ID  }}" 404
```

```sh
docker inspect -f "{{ json .Config }}" 404
```
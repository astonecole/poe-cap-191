# Docker Volume

## Commandes de base

### Créer un volume

```sh
docker volume create your_volume_name
```

### Lister les volumes

```sh
docker volume ls
```

### Supprimer un volume

```sh
docker volume rm your_volume_name
```

### Suprimer les volumes non utilisés

```sh
docker volume prune
```

## Mise en pratique

### Créer un volume pour les données d'une base de données

```sh
docker volume create data_db
```

### Démarrer un container MySQL en spécifiant le volume **data_db** précédemment créé

```sh
docker run --name db -d -e MYSQL_DATABASE=test -e MYSQL_ROOT_PASSWORD=root -v data_db:/var/lib/mysql mysql
```

### Supprimer le container db

```sh
docker rm -f db
```

# Docker container

## Docker volume

### Lister les volumes

```sh
docker volume ls
```

### Créer un volume

```sh
docker volume create db1
```

### Suppression d'un volume

```sh
docker volume create db1
```

Suppression des volumes non utilisés

```sh
docker volume prune
```


## Docker Run

```sh
docker run --name db \
    -e MYSQL_DATABASE=test \
    -e MYSQL_ROOT_PASSWORD=root \
    -v db1:/var/lib/mysql mysql
```

## Docker inspect

```sh
docker inspect -f "{{ .ID  }}" 404
```

```sh
docker inspect -f "{{ json .Config }}" 404
```

```sh
docker run --name db \
    -e MYSQL_DATABASE=test \
    -e MYSQL_ROOT_PASSWORD=root \
    -v db1:/var/lib/mysql mysql
```

#### Connection dans le container MySQL

```sh
docker exec -it db /bin/bash
```

```sh
mysql -u root -p
Password: 
```


```sh
docker run -p 27017:27017 --name mgo -v mongodb:/data/db -d mongo
```

```sh
docker exec -it mgo /bin/bash
```

## Images

- mysql
- phpmyadmin/phpmyadmin


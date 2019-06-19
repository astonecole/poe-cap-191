# Network

## Commandes de bases

### Créer un réseau 

```sh
docker network create --driver bridge aston_network
```

### Lister les réseaux

```sh
docker network ls
```

### Supprimer un réseau

```sh
docker network rm aston_network
```

## Mise en pratique

Pour lier deux containers entre eux, il est nécéssaire des les associer au même réseaux avec l'option **--network** de la commande **run**.

### Démarrage d'un serveur MySQL

```sh
docker run --network aston_network --name db -e MYSQL_ROOT_PASSWORD=root -d mysql --default-authentication-plugin=mysql_native_password
```

```sh
docker run --network aston_network -p 127.0.0.1:8080:80 --name myadmin -e PMA_HOST=db -e PMA_ARBITRARY=1 -d phpmyadmin/phpmyadmin 
```

### Supprimer les containers

```sh
docker rm -f myadmin db
```
# Network

```sh
docker run --network aston_network --name db -e MYSQL_ROOT_PASSWORD=root -d mysql --default-authentication-plugin=mysql_native_password
```

```sh
docker run --network aston_network -p 127.0.0.1:8080:80 --name myadmin -e PMA_HOST=db -e PMA_ARBITRARY=1 -d phpmyadmin/phpmyadmin 
```

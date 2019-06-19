# Docker Machine

Docker machine est un utilitaire permettant de provisionner des machines physiques ou virtuelles. C'est très pratique pour le déploiement.

## Mise en pratique

Pour faire un test de déploiement en local il est nécessaire de créer une machine virtuelle.
La commande à employer varie selon le systeme de virtualisation installer sur votre ordinateur.

### Exemple avec VirtualBox

```sh
docker-machine create --driver virtualbox myserver
```

```sh
docker-machine env myserver
```

### Exemple avec HyperV

Il peut être nécessaire de créer un switch dans hyperv si la commande suivante de suffit pas. Il faut aussi ouvrir un terminal en mode administrateur.

Lire le tutoriel ["Hyper-V Troubleshooting"](https://rominirani.com/docker-machine-windows-10-hyper-v-troubleshooting-tips-367c1ea73c24) pour les problèmes avec hyperv.

```sh
docker-machine create --driver hyperv myserver
```

**Une fois la machine créée, afficher les variables d'environnements :**

```sh
docker-machine env myserver

$Env:DOCKER_TLS_VERIFY = "1"
$Env:DOCKER_HOST = "tcp://10.59.4.19:2376"
$Env:DOCKER_CERT_PATH = "C:\Users\user\.docker\machine\machines\myserver"
$Env:DOCKER_MACHINE_NAME = "myserver"
$Env:COMPOSE_CONVERT_WINDOWS_PATHS = "true"
# Run this command to configure your shell:
# & "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env myserver | Invoke-Expression
```

Pour vous connecter sur la machine distante copier coller la ligne suivante :

```sh
& "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env myserver | Invoke-Expression
```

#### Deploiement de l'application

```sh
docker-compose up -d
```
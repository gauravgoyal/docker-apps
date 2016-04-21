## Webapp direcotry contains docker configuration files, database, apache2 vhost and logs.

## Prerequisite
 - Docker - https://docs.docker.com/engine/installation/
 - Docker compose - https://docs.docker.com/compose/install/
 - Docker hub account - https://docs.docker.com/docker-hub/overview/

## Introduction
 - Infrastructure
  - This app contains apache2 & php5-fpm, memcached, mysql services.
  -  Each service has its own container.
  -  All the containers are interlinked with each other.
 
## Directory Information

### Docker
 - It contains docker files for every image.

### Configuration
 - Dev
  - Contains all the configuration for development site.
 - local
  -  Contains all the configuration for local site.
#### Inside DEV
 - apache2
  - This directory contains virtual hosts for the app.
 - memcached
  - This directory contains configuration file for memcache.
 - mysql
  - This directory contains configuration file for mysql.
  
### Database
 - This directory contains the database files for this app i.e. these files are used by mysql.
 
### logs
 - All the logs are saved into this directory.

## How to use

### Docroot
 - There is a directory called docroot in the repo, put your code inside that directory

### Configuration
 - Local
  - If you want to change / want to have new configuration, add them to local directory. You can use the dev configurations as reference.
### Setup
 - Docker Login
  - Before doing anything, login to docker hub using command ```docker login``` 
 - Infrastructure
  - Goto webapp folder.
  - Run ``` docker-compose up -d ``` and it will set your infrastructure.
 - SSH Keys
  - There is a docker-compose.yml file, in which you will see a variable called "AUTHORIZED_KEYS".
  - repalce its value (```**NONE**```) by your public key.
 - Database setup.
  - Get the sql database file.
  - Put file in database folder of this repo.
  - Login to the docker database container using docker exec command.
  - Run mysql -uroot -p.
  - It will ask for password, and password is supplied using docker-compose.yml file using ```MYSQL_ROOT_PASSWORD``` variable.
  - Use this password to create your users, database, import database.
 - Compose configuration override
  - If you want to override the default docker compose file you can do it using docker compose override file. More info at https://docs.docker.com/compose/extends/ 
 
References:
- Base Image - https://github.com/phusion/baseimage-docker
- Ubuntu Image - https://hub.docker.com/r/innoraft/ubuntu/
- Mysql Image - https://hub.docker.com/_/mysql/
- Memcached Image - https://hub.docker.com/r/innoraft/memcached/
- Apache2 Image - https://hub.docker.com/r/innoraft/apache2/
- Documentation - https://docs.docker.com/

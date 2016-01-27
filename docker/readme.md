# Docker :ship:

### Hello World

`docker run ubuntu /bin/echo "Hello World"`

### Download images :arrow_down:

`docker pull mysql`

`docker pull wordpress`

> find containers on
> [Hub docker](https://hub.docker.com/explore/)

### See images

`docker images`

### See **p**rocess **s**tatus

`docker ps -a`

### Run mysql container (with name)

`docker run --name database -e MYSQL_ROOT_PASSWORD=test123 -d mysql`

### Run wordpress and link to mysql container

`docker run --name blog --link database:mysql -e WORDPRESS_DB_PASSWORD=test123 -p 8080:80 -d wordpress`

> -p `<host>:<container>`

### Stop all process

`docker stop $(docker ps -aq)`

### Start a process

`docker start database`

### Remove all process

`docker rm $(docker ps -aq)`

### Remove an image

`docker rmi mysql`

### Enter inside a container

`docker exec -i -t database bash`

> -i (interactive)

> -t (tty)

### Execute a command inside a container without enter on it

`docker exec -it database ps aux`

### Execute a container transient

`docker run --rm -i -t ubuntu bash`

## Create a new container with commit

`docker run -i -t ubuntu bash`

#### Install apache inside of container

`apt-get update && apt-get install -y apache2`

### Commit the changes

`docker commit -m "Apache install" amazing_hodgkin ubuntu/apache`

### Start the new container

`docker run --rm -it -p 8080:80 ubuntu/apache bash`

#### Start apache inside the container

`apachectl start`

> Entry on [localhost:8080](http://localhost:8080/)

## Create new container with Dockerfile :page_facing_up:

> Use this [file](https://github.com/helioalb/cookbook/blob/master/docker/Dockerfile)

> `docker build -t ubuntu/apache .`

> `docker run -p 8080:80 -d ubuntu/apache`
> A process in a container is **always** a **FOREGROUND**

> ADD unzip file `.zip` automaticaly

## Handle containers with docker-compose :palm_tree:

> Use this [file](https://github.com/helioalb/cookbook/blob/master/docker/blog/docker-compose.yml)

### Start a docker-compose in background

`docker-compose up -d`

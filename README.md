# Docker Tutorial taught by Java Brains.

## Creating containers from images
``` 
1. docker pull alpine --> download alpine from dockerhub.
2. docker run alpine ls --> run ls in alpine containers.
3. docker run -it alpine sh --> run interactive terminal.

```

## docker process
```
1. docker ps --> list of running containers
2. docker ps -a --> list of all running containers
```

## Examining containers in Docker Desktop
```
docker run httpd --> download and run httpd
```

## Docker CLI Recap
```
docker images -- list of available images
```

## Runniing Java with out installing Java
```
docker run -it openjdk bash  --> container with java installed.
```

## Running Nodejs with out installing Nodejs
```
docker run -it node bash
```


## Images vs Containers
```
1. Image is a template and container is its instance.
2. docker save ubuntu -o ubuntu.zip --> saving container instance.
3. Do not tweak a container, rather change image and build container from that modified image.
4. latest is a tag. It is just a name. usually to track version
```

## Managing running containers
```
1. docker ps  --> list af all running process/ containers.
2. docker stop <container id> --> request to stop containers.
3. docker kill <conatainer id> --> force kill running conatainers.
4. docker run -it --name myopenjdk openjdk bash --> giving name to containers.
5. docker rm <container id> --> remove running containers.
6. docker commit  --> save instance conatiners. Herdly used. Use docketfile instead.
7. docker start <conatiner_id> --> start the stop process. Pick up from the given state.
```

## Detach from and Attach to running containers
```
1. docker run -d httpd  --> run in background and do not take the terminal 
```

## docker exec
```
Run command in a running conatainer
docker exec <container id> ls
```

## docker --rm to remove container automatically.
```
docker run -it --rm alpine sh
```


## running MySQL server with Docker
```
1. docker run --name my-mysql -d -e MYSQL_ROOT_PASSWORD=TestinG123@ mysql

Description:
--name: giving name
-d: detach it
-e: set environment variable


2. docker exec -it my-mysql bash
Description: getting into bash of that conatainer.

3. mysql -u root -p 
Description: logging into mysql.

```

## Mounting a host folder using docker volume
```
docker run --name my-openjdk -it -v ${PWD}:/hostvol openjdk bash

DESCRIPTION:
-v: volume mount
-it: interactive terminal
--name: giving. 

For Windows: (CMD)
docker run --rm -it -v %cd%:/usr/src/project gcc:4.9

For Windows : (Powershell)
docker run --rm -it -v ${PWD}:/usr/src/project gcc:4.9

For Linux: 
docker run --rm -it -v $(pwd):/usr/src/project gcc:4.9

```

# Learning Links
* [Docker Tutorial for Beginners - A Full DevOps Course on How to Run Applications in Containers](https://www.youtube.com/watch?v=fqMOX6JJhGo)
* [Docker Docs](https://docs.docker.com/get-started/)
* [Public Docker Images Repo](https://hub.docker.com/)
* [Online Labs URL for Executing commands](https://kodekloud.com/p/docker-labs)

[docker-for-java-developers](https://www.linkedin.com/learning/docker-for-java-developers/run-your-first-docker-container?u=42751868)

[Docker Tutorial for Beginners [FULL COURSE in 3 Hours]](https://www.youtube.com/watch?v=3c-iBn73dDE)

# Important Commands
## RUN - Start a container
#### It will create the container of the image which is present locally. If its not not there locally, it will go and pull from the public docker repo
```
$ docker run nginx

$ docker run --name webapp nginx:1.14-alpine
  This will give name to the created container as webapp

$ docker run -d --name webapp nginx:1.14-alpine

$ docker run redis:4.0  --> 4.0 is the tag

$ docker run -i kodekloud/simple-prompt-docker
    i stands for interactive mode. This will map the stand input of container to the standand input of the host
$ docker run -it kodekloud/simple-prompt-docker
    This will map the stand input and terminal of container to the standand input of the host
```

## PS - list containers
```
$ docker ps -> lists only running Containers
$ docker ps -a -> lists all containers (running + stopped)
```

## STOP - stops a container
```
$ docker stop <container_name>
$ docker stop <contianer_id>
```

## RM - Removes a container
```
$ docker rm <container_name>
$ docker rm <contianer_id>
```

## IMAGES - Lists images
```
$ docker images
```

## RMI - Remove images
#### Note: Delete all dependent containers to remove image
```
$ docker rmi <image_name>
```
## PULL - downlad an image
```
$ docker pull nginx
```
## EXEC - execute a command
```
$ docker run ubuntu sleep 100
$ docker exec <container_name> cat /etc/hosts
```
## RUN - attach and detach
```
$ docker run ngnix
   This will run the container in attached mode, where output of this container is getting printed in the terminal and you will not be able to use the terminal for anything.

$ docker run -d ngnix
  This will run the container in the detached mode by creating the <container_id>.. Here you can use the same terminal for some other work.

$ docker attach <container_id>
  This will attach the detached container back.
```

##  RUN - Port forwarding
The underlying host where the docker is intstalled is called as docker host or docker engine

Everytime a container is created, an internal ip will be assigned to the container. Since ip is internal, its accessible only inside the docker host. if things needs to be accessed outside the docker host , then we need to do port forwarding
```
$ docker run kodekloud/webapp
  * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)

$ docker run -p 80:5000 kodekloud/webapp
```

## RUN - Volume mapping
```
$ docker run mysql
$ docker stop mysql
$ docker rm mysql
  Without volume mapping, everytime continer is destroyed/removed, all the data inside the container will be destroyed. To keep the backup of the data, we need to do volume mapping

$ docker run -v /opt/datadir:/var/lib/mysql mysql
```

## Inspect Container
```
$ docker inspect <container_name>
$ docker inspect <container_id>
```
## Container logs
```
$ docker logs <container_name>/<container_id>
```

## ENV Variables in docker
```
$ docker run -e APP_COLOR=blue simple-webapp-color
$ docker run -e APP_COLOR=red simple-webapp-color  

$ docker inspect <container_name>/<container_id>
  Using this, we can see the already set environment variables of the docker container
```

## How to copy Docker images from one host to another without using a repository
[How to copy Docker images from one host to another without using a repository](https://stackoverflow.com/questions/23935141/how-to-copy-docker-images-from-one-host-to-another-without-using-a-repository)

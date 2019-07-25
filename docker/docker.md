# Docker

## Intro

## Installation
* Add GPG key for the official Docker repo
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
* Add the docker repo to apt sources
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
* Update package database with docker packages
```
sudo apt-get update
apt-cache policy docker-ce
```
* Install Docker
```
sudo apt-get install -y docker-ce
```
* check the status of docker
```
sudo systemctl status docker
```
### Docker Command without sudo
```
sudo usermod -aG docker ${USER}
su - ${USER}
```
* following command should show docker 
```
id -nG
```

## Docker Useful commands
* 
```
docker info
```
* To check whether downloading images from docker hub
```
docker run hello-world
```
* Search 
```
docker search ubuntu
```
* Pull image
```
docker pull ubuntu
```
* Run a container
```
docker run ubuntu
```
* List downloaded images
```
docker images
```
## Docker Container useful commands
* Interactive shell
```
docker run -it ubuntu
```
* Managing docker containers
```
docker ps
```
* To view all containers(archive)
```
docker ps -a
```
* To view the latest container
```
docker ps -l
```
* start a container
```
docker start <container_id>
or 
docker start <container_name>
```

* stop a container
```
docker stop <container_id>
or 
docker stop <container_name>
```

* Remove a container
```
docker rm <container_id>
or
docker rm <container_name>
```

* Committing Changes 
```
docker commit -m "message comes here" -a "author name" <container-id> repo/<new-image-name>
``` 
e.g.,
docker commit -m "added node.js" -a "sammy" d9b100f2f636 sammy/ubuntu-nodejs

* Pushing Docker Images to a Docker Repo
```
docker login -u <docker_registry_username>
and
docker push <username>/<image_name>
```


## References
[1]. [Installation and Use of Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04)

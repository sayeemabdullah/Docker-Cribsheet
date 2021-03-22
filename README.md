# Docker-Cribsheet

> I just started learning **Docker** so this is just a small initiative to make a crib sheet that may help me or anyone else in the future. You can also check out my [CSS Cribsheet](https://github.com/sayeemabdullah/CSS-Cribsheet) and [React Cribsheet](https://github.com/sayeemabdullah/React-Cribsheet).

___

## Installation

To install we need to run the following command:

``` bash

$ sudo apt install docker.io

```

To check we can run the following command:

``` bash

sudo docker run docker/whalesay cowsay github.com/sayeemabdullah

```

If the installation was completed successfully we will see a whale saying “github.com/sayeemabdullah”.

After installation, we might not be able to use the commands without the keyword `sudo`. Now to run the docker without the root we can use the following commands:

``` bash

$ sudo groupadd docker

$ sudo usermod -aG docker $USER

$ newgrp docker

```
If the last command doesn’t work reboot your machine and try again. 

___

## Docker Commands

* **docker version** - shows docker version

* **docker run name_of_the_image** - starts a container

* **docker run name_of_the_image:name_of_the_tag** - starts specific version of a container

* **docker run name_of_the_container sleep number_of_seconds** - container sleeps after n second

* **docker ps** - shows a list of running containers

* **docker ps -a** - shows list of all containers (stopped & running)

* **docker stop name_of_the_container** - stops a container

* **docker rm name_of_the_container** - removes a container

* **docker images** - shows list of images

* **docker rmi name_of_the_image** - removes an image

* **docker pull name_of_the_image** - downloads an image

* **docker exec name_of_the_container cat /etc/hosts** - executes a command

* **docker attach name_or_id_of_the_container** - runs a container in attach mode

* **docker run -d name_of_the_container** - runs a container in detach mode

* **docker run -it name_of_the_container** - runs a container with `i`--> interactive and `t`--> terminal mode

* **docker run -p port_number_of_local_host`:`docker_container_port name_of_the_container** - maps `port_number_of_local_host` to `docker_container_port`

* **docker run -v directory/outside/the/container`:`directory/inside/the/container name_of_the_container** - mounts the `directory/outside/the/container` to `directory/inside/the/container`

* **docker inspect name_of_the_container** - returns details in a JSON format

* **docker logs name_or_id_of_the_container** - returns logs of the container
___

## Docker Images

Before creating the docker image we have to create a **docker file** call it **Dockerfile**. After creating the docker file we will create an image with the docker command. 

### Dockefile

Docker file is a text file that consists of two parts instructions and arguments.

``` text

FROM Ubuntu		// Start from a base operating system or another image 

RUN agt-get update	// Intsall all dependencies 
RUN agt-get install python	// Install all dependencies 

RUN pip install flask	// Install all dependencies 
RUN pip install flask-mysql	// Install all dependencies 

COPY . /opt/source-code	// Copy source code

ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask run	// Specify Entrypoint

```

___

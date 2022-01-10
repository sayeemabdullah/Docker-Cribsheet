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

$ sudo docker run docker/whalesay cowsay github.com/sayeemabdullah

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

* **docker run -d --name name_of_the_container name_of_the_image** - starts a container with a name

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

* **docker run -it name_of_the_container** - runs a container with `i`nteractive and `t`erminal mode

* **docker run -p port_number_of_local_host`:`docker_container_port name_of_the_container** - maps `port_number_of_local_host` to `docker_container_port`

* **docker run -v directory/outside/the/container`:`directory/inside/the/container name_of_the_container** - mounts the `directory/outside/the/container` to `directory/inside/the/container`

* **docker inspect name_of_the_container** - returns details in a JSON format

* **docker logs name_or_id_of_the_container** - returns logs of the container

* **docker run -e variable_name=value_to_set** - run container by setting an environment variable

* **docker run --link name_of_container_to_link:name_of_container_to_link name_of_the_image** - run image by linking with container(s)

* **docker-compose up** - build the docker compose file 
___

## Docker Images

Before creating the docker image we have to create a **docker file** call it **Dockerfile**. After creating the docker file we will create an image with the docker command. 

### Dockerfile

Docker file is a text file that consists of two parts instructions and arguments.

``` text

FROM Ubuntu     // Start from a base operating system or another image 

RUN agt-get update      // Install all dependencies 
RUN agt-get install python      // Install all dependencies 

RUN pip install flask     // Install all dependencies 
RUN pip install flask-mysql     // Install all dependencies 

COPY . /opt/source-code     // Copy source code

ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask run      // Specify Entrypoint

```

Docker file works in layers. If any layer fails then the docker will reuse the previous layers from the cache and start from when it failed. 

### Creating & Pushing Docker Image Command

To create an image locally we will use the following command:

``` shell

docker build Dockerfile -t name/imageName

```

And to push the image to **Docker Registry**, we will use the following command:

``` shell

docker push accountName/imageName

```   

___

### Commands vs Entrypoint

ENTRYPOINT represents an entrypoint and CMD represents commands in Dockerfiles. 

To make our container execute a command, we use *CMD command param* or *CMD ["command","param"]*. However, if we want to pass the parameter from the command line, we can use entrypoints like ENTRYPOINT["command"]. The container will fail to run without passing a parameter after doing this, so in order to fix this, we can use CMD["param"] for setting a default parameter.

___

### Docker Compose

We will make a `YAML` docker-compose file where there will be a dictionary of container names where we will write the name of the images, ports and links as follows:

![Screenshot 2022-01-10 at 10 24 23 AM](https://user-images.githubusercontent.com/31423599/148718298-842494ed-76ab-45c5-9598-af817ac2584a.png)

This is version 1, and for version 2 & 3 everything will be under 'Services'. Version must be specified on top. We can also add networks like the following: 


![Screenshot 2022-01-10 at 1 08 26 PM](https://user-images.githubusercontent.com/31423599/148729109-a854a894-bfb4-4bbc-920f-915720b39d66.png)


___

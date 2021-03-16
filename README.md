# Docker-Cribsheet

> I just started learning **Docker** so this is just a small initiative to make a crib sheet that may help me or anyone else in the future. You can also check out my [CSS Cribsheet](https://github.com/sayeemabdullah/CSS-Cribsheet) and [React-Cribsheet](https://github.com/sayeemabdullah/React-Cribsheet).


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

## Simple Docker Commands

* **docker run name_of_the_image** - start a container
* **docker run name_of_the_image:name_of_the_tag** - start specific version of a container
* **docker ps** - shows list of running containers
* **docker ps -a** - shows list of all containers (stopped & running)
* **docker stop name_of_the_container** - stop a container
* **docker rm name_of_the_container** - remove a container
* **docker images** - shows list of images
* **docker rmi name_of_the_image** - remove an image
* **docker pull name_of_the_image** - download an image
* **docker run name_of_the_container sleep number_of_seconds** - container sleeps after n second
* **docker exec name_of_the_container cat /etc/hosts** - execute a command
* **docker run -d name_of_the_container** - run a container in detach mode
* **docker attach name/id_of_the_container** - run a container in attach mode
* **docker version** - shows docker version





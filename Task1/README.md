# Using images
## Overview
In this task we will:
- download an image with scipy and jupyter lab preinstalled
- run a container
- test how containers work
- delete both the container and the image

This task should be done with a teacher, listening to the lecture will help you understand the content.

## Instructions

- Run Powershell

```
docker image ls
docker pull jupyter/scipy-notebook
docker image ls
docker run -it -p 8888:8888 jupyter/scipy-notebook
```
- Open the link you see on the screen with your browser, or enter http://localhost:8888 and enter the token
- Create new notebook
- Copy and run this example: https://docs.scipy.org/doc/scipy/tutorial/interpolate.html
- Shutdown container (ctrl+C)
```
docker ps
docker ps -a
docker start <your_container_name>
```
- Open the link you see on the screen with your browser, or enter http://localhost:8888 and enter the token. Please, check if you have your code.
```
docker ps
docker ps -a 
docker stop <your_container_name>
docker ps
docker ps -a
docker rm <your_container_name>
docker ps -a
docker image ls
```
- **TO DO: run new jupyter/scipy-notebook container. Do you have your code?**
- **TO DO: remove your image**
```
Docker run -it –rm jupyter/scipy-notebook /bin/bash
$ls
$pwd
$exit
docker image rm jupyter/scipy-notebook
```
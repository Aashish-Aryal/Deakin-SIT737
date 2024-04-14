# Week 5 step-by-step instructions

## Step 1
Install Docker and WSL(for Windows)

## Step 2
Create a node app with at least one endpoint. I have copied the calculator app from Week 4.

## Step 3
Create dockerfile. The code for dockerfile is given by the tutor.

## Step 4
Login/Signup to DockerHub

## Step 5
Build the docker image using `docker build -t <username>/<image_name>:<tag> .`.

## Step 6
Run the docker image using `docker run --name <container_name> -p <local_port>:<docker_port> <username>/<image_name>:<tag>`.

## Step 7
Check if the docker container is running using `docker ps`.

## Step 8
You can see the logs of the docker container or the output printed by the app on the container terminal using `docker logs <container_id>`.

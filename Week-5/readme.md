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

## Now Docker compose

## Step 9
Create a docker-compose.yml file. This file contains information about all the containers that needs to be created, which image do the containers use, their ports, networks, ect.

## Step 10
Run the docker compose file using the command `docker compose up`.

## Step 11
To see both containers are running and can be accessed, log on to localhost using the external ports accessed by both the apps as mentioned in the **docker-compose.yml** file. It's 3043 and 3044 in this case.

## Step 12
Get the ip address of one docker container and ping that container from the next container so show that both containers can communicate with each other. <br>
`docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container1_name>` to get the IP address of 1st container. <br>
`docker exec -it <container2_name> /bin/bash` and `ping <container1_IPaddress>` to ping one container from the another container.

## Now pushing the docker image to dockerhub

## Step 13
Login to dockerhub using the command `docker login` and enter the id and password of your dockerhub account.

## Step 14
Push the docker image to dockerhub using the command `docker push <username>/<image_name>:<tag>`

## Health check

## Step 15
Add the health check part to both containers in the docker compose file. Stop the docker compose using `docker comose down` and now start the new docker compose with health check using `docker compose up`. We can see the regular health check being conducted at the mentioned interval in the terminal. <br><br>

In this health check both the containers are being accessed using `curl` command. The healthcheck is conducted at every 30 seconds. The healthcheck waits for the maximum of 10 seconds before sending the next `curl` request if it does get any response in the 10 seconds, it sends another request. This is repeated for maximum of 3 times and if the healthcheck does not get any response for 3 times, the container is declared to be unhealthy and is restarted.
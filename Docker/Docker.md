- To create a ***Docker Image*** based on the instructions written in a `Dockerfile`
```sh
docker build -t [IMAGE_NAME:TAG_NAME] [Dockerfile_PATH]
### EXAMPLE :
### docker build -t myappimg .
```
>*Sample `Dockerfile` structure:*
```dockerfile
From node:16-alpine

WORKDIR /app

RUN npm install

COPY . .

EXPOSE 4000

CMD ["node", "app.js"]
```
> While writing the Dockerfile it is a good practice to make notice of the order of the instruction written in the file to make use of Docker's ==**Layer Caching**== in the best way possible

- To list docker images installed on the local machine
```sh
docker images
```
- To delete images
```sh
docker image rm [IMAGE_NAME]
```
- To delete containers
```sh
docker container rm [CONTAINER_NAME]
```
- To create and run a container based of a local image
```sh
docker run [IMAGE_NAME]
docker run --name [CONTAINER_NAME] [IMAGE_NAME] # GIVING A NAME TO THE CONTAINER
docker run --name [CONTAINER_NAME] --rm [IMAGE_NAME] # REMOVES THE CONTAINER MADE IN THIS STEP AS SOON AS IT STOPS
docker run --name [CONTAINER_NAME] -p [LOCAL_PORT:CONTAINER_PORT] [IMAGE_NAME] # MAPPING PORTS FROM CONTAINER TO LOCAL COMPUTER
docker run --name [CONTAINER_NAME] -d [IMAGE_NAME] # DETACHING THE CONTAINER FROM COMMANDLINE SO IT WON'T BLOCK CLI
docker run --name [CONTAINER_NAME] -v [LOCAL_MACHINE_FULL_PATH:CONTAINER_FULL_PATH] [IMAGE_NAME] # CREATE A VOLUME RELATIONSHIP BETWEEN THE PATH SPECIFIED IN THE DOCKER CONTAINER AND LOCAL MACHINE
docker run --name [CONTAINER_NAME] -v [CONTAINER_FULL_PATH] [IMAGE_NAME] # CREATES AN ANONYMOUS VOLUME THAT REPRESENTS A FOLDER IN THE CONTAINER THAT SHOULD NOT BE CHANGED BY ANOTHER VOLUME DEFINITION. More Info: The Net Ninja Docker Course - #10 Volumes

```
- To show a list of containers
```sh
docker ps # THIS ONLY SHOWS CONTAINERS THAT ARE CURRENTLY RUNNING
docker ps -a # SHOWS ALL THE CONTAINERS CURRENTLY STORED ON THE LOCAL HOST
```

- To stop a docker container process
```sh
docker stop [CONTAINER_NAME]
```
- To run an existing container
```sh
docker start [CONTAINER_NAME] # PORT MAPPING AND OTHER CONFIGURATIONS ARE NOT NEEDED IN THIS STEP
```

- To remove EVERYTHING from the Docker (Images, Containers, and Volumes get deleted)
```sh
docker system prune -a
```

- Using `docker-compose` commands
```sh
docker-compose up
docker-compose down
docker-compose down --rmi all -v
```
- A file called `docker-compose.yaml` should be placed in the root folder for multiple projects that you want to run images of in the same time. The structure of the file is like this:
```yaml
version: "[DOCKER_COMPOSE_VERSION]"
services:
	[IMAGE_NAME]:
		build: [PATH_TO_DOCKERFILE_FOR_IMAGE_TO_BE_CREATED]
		container_name: [CONTAINER_NAME]
		ports:
			- [LOCAL_PORT:CONTAINER_PORT]
		volumes:
			- [LOCAL_MACHINE_RELATIVE_PATH:CONTAINER_RELATIVE_PATH]
			- [CONTAINER_RELATIVE_PATH]
		
```
- To access the CLI of the container's OS:
```sh
docker exec -it [CONTAINER_NAME] bash
```
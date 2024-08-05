# coding-project-template

# Pull an Image from Docker Hub and run it as a container
docker pull hello-world
- pull your first image from docker hub

docker images
- list your images

docker run hello-world
- run the hello world image as a container
- you should see a 'Hello from Docker!' message in your terminal

docker ps -a
- list the containers to see that your container ran and exited successfully

docker container rm <container_id>
- remove the container with the specified id

# Build an Image using Dockerfile
The following are required to run a Node.js app in a container
- app.js (the main application)
- package.json defines the dependencies
- Dockerfile defines the instructions Docker uses to build the image

docker build . -t myimage:v1
- build the image

docker images
- list images to see your image tagged myimage:v1 in the table

docker run -dp 8080:8080 myimage:v1
- run your image as a container

docker stop $(docker ps -q)
- stop the container with the specified id
- docker ps -q is used to pass a list of all running containers

docker ps
- check to see if the container has stopped running

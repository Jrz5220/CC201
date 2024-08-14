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

# Deploy the application to Kubernetes

Export your namespace as an environment variable: export MY_NAMESPACE=sn-labs-$USERNAME

Build and push your image: docker build -t <...>/$MY_NAMESPACE/hello-word:1 . && docker push <...>/$MY_NAMESPACE/hello-world:1

To view your namespace, enter: echo $MY_NAMESPACE

Insert your namespace in CC201/labs/3_K8sScaleAndUpdate/deployment.yaml file where is says <my_namespace>

Run your image as a Deployment: kubectl apply -f deployment.yaml

List Pods until STATUS is "Running": kubectl get pods

Expose the application to the internet via Kubernetes Service: kubectl expose deployment/hello-world (This creates a service of type ClusterIP)

# Docker 

# install Docker in linux
1. sudo apt-get update
// check suitable versions for the system  apt-cache madison docker-ce
2. sudo apt-get install docker-ce=<version name> docker-ce-cli=<version name> containerd.io
3. verify that docker engine is installed
    sudo docker run hello world
    o/p
    Hello from Docker!
    This message shows that your installation appears to be working correctly.

    To generate this message, Docker took the following steps:
    1. The Docker client contacted the Docker daemon.
    2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
        (amd64)
    3. The Docker daemon created a new container from that image which runs the
        executable that produces the output you are currently reading.
    4. The Docker daemon streamed that output to the Docker client, which sent it
        to your terminal.

# uninstall docker from linux
1. sudo apt-get purge docker-ce docker-ce-cli containerd.io
2. sudo rm -rf /var/lib/docker
3. sudo rm -rf /var/lib/containerd

# Restart the Docker daemon.

 sudo service docker restart

## To automatically start Docker and Containerd on boot for other distros, use the commands below:

 sudo systemctl enable docker.service
 sudo systemctl enable containerd.service

## To disable this behavior, use disable instead.

 sudo systemctl disable docker.service
 sudo systemctl disable containerd.service

## Topics
1. build and run an image as a container
2. Share image using docker hub
3. deploy docker image using multiple container with database
4. running application with docker compose


## why docker
1. so many servers, databases, securities patches, machines,sever missed complete nightmare to trouble shoot.
2. all machines are not updated so it gives an errors
3. docker rescue, application backed up and pull and run again 

## sollutions
1. builing images : consistently package everything your application needs to run
2. shiping images : easily ship this images into runtime cloud or local env.
3. runnitn images : easily and consistently run the images
4. CI/CD : consistently test and deploy your code in different env : - stage,UAT,prod
5. different versions:  easily run different version without installing
6. Roll Forward: when defect found no need to patch or update the application, ship new image and run


## check version
docker version

docker run is there why we need docker-compose.yml
when need multiple images that time docker-compose.yml file is used


## How to create an image file
1. create express project
2. create DockerFile within project (check DockerFile in project)
3. create docker image in local
docker build --tag image-name .
so here . will take existing directory else we have to set the path of our dir
4. to update image execute above command which will override the changes into same images
5. create container and run that image within container
docker run --name container-name -p hostPort:guestPort image-name

## what is a container? 
Simply put, a container is simply another process on your machine that has been isolated from all other processes on the host machine. That isolation leverages kernel namespaces and cgroups, features that have been in Linux for a long time. Docker has worked to make these capabilities approachable and easy to use.

## create container 
 > docker build -t getting-started .

 
## What is a container image?¶
When running a container, it uses an isolated filesystem. This custom filesystem is provided by a container image. Since the image contains the container's filesystem, it must contain everything needed to run an application - all dependencies, configuration, scripts, binaries, etc. The image also contains other configuration for the container, such as environment variables, a default command to run, and other metadata.


## pluralsight
1. Native orchestration
2. Declarative service model
3. Scale services
4. rolling applications updates
5. stacks and bundles

clustering and orchestration features introduced in docker 1.2


scan images for security vulnerabilities ?

How to deploy docker application with multiple database container ?

Running application with docker compose ?


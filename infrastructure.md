
# docker

The most important concepts in Docker include containers, images, and volumes. A container is a runtime instance of an image, which is a lightweight, stand-alone, executable package of software that includes everything needed to run an application, including the code, runtime, system tools, system libraries, and settings. Lastly, a volume is a directory or file system mount which is used to store data that is not stored in the container image. Together, these concepts form the basis of Docker and enable it to be used for creating and running applications in isolated environments.

## Docker CLI
```
docker run # Create a container from an image and start it
docker ps # List containers
docker images # List images
docker rmi # Remove one or more images
docker rm # Remove one or more containers
docker exec -it <container> bash # Run a command in a running container with bash interactive terminal
docker logs <container> # Fetch the logs of a container
docker stop <container> # Stop one or more running containers
docker start <container> # Start one or more stopped containers
docker build # Build an image from a Dockerfile
docker pull # Pull an image or a repository from a registry
docker push # Push an image or a repository to a registry
docker network create # Create a network
docker network connect # Connect a container to a network
```

## Dockerfile
```Dockerfile
# The FROM statement specifies the base image used for building the Docker image.
FROM ubuntu:20.04

# The RUN statement is used to execute commands and create new layers in the image.
RUN apt-get update && apt-get install -y curl

# The CMD statement specifies the command to be executed when the container is started.
CMD ["curl", "-s", "https://example.com"]

# The ENTRYPOINT statement specifies the command to be executed when the container is started.
ENTRYPOINT ["/usr/bin/curl"]

# The ENV statement is used to set environment variables.
ENV PATH="/usr/local/bin:$PATH"

# The LABEL statement is used to add metadata to the image.
LABEL maintainer="John Doe <john.doe@example.com>"

# The ARG statement is used to declare arguments that can be passed to the image.
ARG VERSION=1.0.0

# The COPY and ADD statements are used to copy files and directories from one location to another.
COPY index.html /var/www/

# The VOLUME statement is used to create a mount point for external storage.
VOLUME /var/www/data

# The USER statement is used to set the user for running the container.
USER www-data

# The WORKDIR statement is used to set the working directory for the container.
WORKDIR /var/www/

# The EXPOSE statement is used to expose ports to the host machine.
EXPOSE 80

# The HEALTHCHECK statement is used to check the health of the container.
HEALTHCHECK --interval=30s --timeout=3s \
  CMD curl -f http://localhost/ || exit 1
```
## docker compose
A typical Docker Compose file contains configuration options for the services that make up your application. It is written in YAML and contains the following elements: version, services, networks, volumes, and configs.

The version element specifies the version of the Compose file that is being used.

The services element defines the services that will be used in the application. It includes the image used for the service, the ports used to access the service, any environment variables associated with the service, and any networks that the service will join.

The networks element defines the networks that will be used by the application. It includes the driver used to create the network and the IP address configuration for the network.

The volumes element defines the data volumes that will be used in the application. It includes the source and target locations for the volumes, as well as any permissions associated with them.

The configs element defines configuration files that will be used by the application. It includes the source and target locations for the configuration files, as well as any permissions associated with them
```yaml
version: '3.7' # Specifies the version of the Compose file

services: # Defines the services that will be used in the application
  web: # Name of the service
    image: nginx:alpine # Image used for the service
    ports: # Ports used to access the service
      - "8080:80" # Maps port 8080 on the host to port 80 on the container
    environment: # Environment variables associated with the service
      - NGINX_HOST=localhost
      - NGINX_PORT=80
    networks: # Networks the service will join
      - webnet

networks: # Defines the networks that will be used by the application
  webnet:
    driver: bridge # Driver used to create the network
    ipam:
      driver: default # IP address configuration for the network
      config:
        - subnet: 192.168.2.0/24

volumes: # Defines the data volumes that will be used in the application
  data_volume: # Name of the volume
    driver: local # Driver used to create the volume
    driver_opts: # Options for the driver
      type: nfs
      device: :/path/to/nfs/share
      o: addr=192.168.1.100,rw

configs: # Defines configuration files that will be used by the application
  config_file: # Name of the configuration file
    file: ./config/config.json # Source location of the configuration file
    target: /config/config.json # Target location of the configuration file
    mode: 0444 # Permissions associated with the configuration file
```
## docker networking 
Container-level networking is used to connect multiple containers to one another on the same host. It is the default network type in Docker and allows containers to communicate with each other, as well as other processes on the host.

Bridge networking is used to connect multiple containers running on different hosts in a single network. This type of network allows containers to communicate with each other, as well as other processes on the host. It also enables secure communication between containers on different hosts.

Overlay networking is used to span multiple hosts. It allows for secure communication between containers on different hosts. Additionally, it enables containers to communicate with each other and other processes on the host. It is used when you need to connect multiple containers running on different hosts in a single network.

## container orchestration

### kubernetes

kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications.

#### docker swarm

docker swarm is a native clustering tool for Docker. It turns a pool of Docker hosts into a single, virtual Docker host.

# git

```
git remote add origin git@github.com:nicholashobbs/knawlige.git
git branch -M main
git push -u origin main

```


## create repo for github

`git init -b main` to initialize a git repo

`git add . && git commit -m "initial commit"`

`gh repo create` to create a repo on github

git remote add origin git@github.com:nicholashobbs/react-inventory.git


get private email from settings > email

ssh-keygen -t ed25519 -C "email@example.com"

`git config --global user.email "email"` to set email
`git config --global user.password "password"` to set password

`git log --graph` to see the history of the repo
`git log --graph --oneline` to see the history of the repo in one line

`git reflog` to see the history of the repo in detail including actions leading to commits

`git status` to show current status and merge conflicts

`git diff --staged` to see the changes that are staged
`git diff` to see the changes that are not staged

`git reset <sha>` to reset to a previous commit
`git switch -c <branch>` to create a new branch
`git switch <branch>` to switch to a branch

`git reset --hard <sha>` to reset to a previous commit and discard all changes

`git restore <file>` to discard changes to a file
`git commit --amend` to amend the last commit

`git checkout <sha> <file>` to checkout a file from a previous commit

`git stash list`

`git add .` to stage all changes
`git commit -m "message"` to commit changes
`git push origin branch` to push changes to remote branch

`git pull origin branch` to pull changes from remote branch - pull updates current HEAD to match the remote branch
`git fetch origin branch` to fetch changes from remote branch - fetch downloads commits, files, and refs from a remote repository into your local repo without merging them




# ci/cd
# elastic
# redis
# aws
# terraform

# angular-docker-base
Nginx based docker setup for angular projects.

## Setup the repo:
The repo contains a minimal Angular project. The sourcecode of that dummy project is separeted in a folder called DockerizedAngularProject. If you want containerize your Angular project, just:

1. Copy all the files near you project's folder, except the DockerizedAngularProject and .git folders and except the README.md and .gitignore files.
2. Do a little setup on the Dockerfile and docker-compose.yml files. You should rename the DockerizedAngularProject directory in the Dockerfile to your project's directory name. Also, you probably want to rename the dockerized-angular-project occurances in the docker-compose.yml to your flavor.

## Build and start your dockerized project
The easiest way to start the container is via the docker-compose. I do not recommend to use the 'docker run'. To start the container, just do:

        docker-compose up

To start it in detached mode, so it won't block the terminal:

        docker-compose up -d

## Some useful takeways to highlight

* Note the Dockerfile is a multistage one. It is always a good thing to separete the build stage from the artifact stage. You will got a much smaller image at the end.
* Never forget the .dockerignore file. You don't want to copy node_modules folder anywhere, trust me.

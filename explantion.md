# IP 2 explanation for the E-Commerce aplication website

![Snippet](/home/phillis/Pictures/Ecommerse.png)

## 1. Choice of the base image on which to build each container.
-Client /Frontend: Based on node:18-alpine for builds and nginx:alpine for serving the static files.
-Backend: Used node:18-alpine to minimize image size while maintaining compatibility with Node.js dependencies.
-Database:  "MONGO_VERSION=8.0.8", the mongo:latest for stability and built-in volume support.


## 2. Dockerfile directives used in the creation and running of each container.
-For mongo container:
    1. CMD: Specify default commands.
    2. WORKDIR: Creating/Change working directory.
    3. ENTRYPOINT: Specify default executable.
    4. VOLUMES: Create volume mounts.
    5. ENV: Set environment variables.
    6. ONBUILD: Specify instructions for when the image is used in a build.
    7. RUN: Execute build commands. Installs dependencies (only production for backend).
    8. COPY brings in project files.

-For brianbwire/brian-yolo-client:v1.0.0 container: 
    1. ENV
    2. CMD
    3. VOLUMES
    4. WORKDIR
    5. ENTRYPOINT
    6. ONBUILD
    

## 3. Docker-compose Networking (Application port allocation and a bridge network implementation) where necessary.
- For the Ports, we have:
    Clint /Frontend exposed on 3000:3000
    Backend exposed on 5000:5000
    Mongo on 27017:27017
- All services use a shared bridge network called app-network.


## 4. Docker-compose volume definition and usage (where necessary).
- MongoDB uses volumes for persistent data:
"Volumes": 
                "/data/configdb": {},
                "/data/db": {}


## 5. Git workflow used to achieve the task.
Used Git to track the progress of this project from setup to deployment.

    Initialized Git in the project directory using git init.
    .gitignore file added to ignore unnecessary files like node_modules, environment configs, and logs.
    Made at least 10 descriptive commits, for example:
    init backend Dockerfile
    add docker-compose.yml
    set up MongoDB service
    build and push Docker images
    Created a clean folder structure:
    /backend
    /client
    docker-compose.yml
    .gitignore
    README.md

## 6. Successful running of the applications and if not, debugging measures applied.
    Application run successfully using: http://172.17.0.2:3000/  /home/phillis/Pictures/Ecommerse.png


## 7. Good practices such as Docker image tag naming standards for ease of identification of images and containers. 
- put something

## 8. There is a screenshot of your deployed image on DockerHub, clearly showing the version of the image
- put something
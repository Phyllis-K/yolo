# IP 2 explanation for the E-Commerce aplication website

![Banner](/home/phillis/Pictures/Ecommerse.png)

## 1. Choice of the base image on which to build each container.
-Client /Frontend: Based on node:18-alpine for builds and nginx:alpine for serving the static files.
-Backend: Used node:18-alpine to minimize image size while maintaining compatibility with Node.js dependencies.
-Database: Used official mongo:latest for stability and built-in volume support.


## 2. Dockerfile directives used in the creation and running of each container.
- CMD or ENTRYPOINT launches the app.
- WORKDIR defines the default folder for container operations.
- RUN installs dependencies (only production for backend).
- COPY brings in project files.


## 3. Docker-compose Networking (Application port allocation and a bridge network implementation) where necessary.
- For the Ports, we have:
    Clint /Frontend exposed on 3000:3000
    Backend exposed on 5000:5000
    Mongo on 27017:27017
- All services use a shared bridge network called app-network.


## 4. Docker-compose volume definition and usage (where necessary).
- MongoDB uses volumes for persistent data:
volumes:- mongo-data:/data/db


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
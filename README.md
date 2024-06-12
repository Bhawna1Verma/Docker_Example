# Getting started

This repository is a sample application for users following the getting started guide at https://docs.docker.com/get-started/.

The application is based on the application from the getting started tutorial at https://github.com/docker/getting-started


commands used to run the docker file in git bash to customize an app:
1. Get the app
$ git clone https://github.com/docker/getting-started-app.git
2. Build the app
$ cd /path/to/getting-started-app
$ touch Dockerfile
 add the command in docker file
 syntax=docker/dockerfile:1

    FROM node:18-alpine
    WORKDIR /app
    COPY . .
    RUN yarn install --production
    CMD ["node", "src/index.js"]
    EXPOSE 3000
$  cd /path/to/getting-started-app
3. Build the image
$  docker build -t getting-started .
4. Start the app container
$  docker run -dp 127.0.0.1:3000:3000 getting-started
$  docker ps

# Update the application 
    1.    Update the source code:

        In the src/static/js/app.js file, update line 56 to use the new empty text.


        - <p className="text-center">No items yet! Add one above!</p>
        + <p className="text-center">You have no todo items yet! Add one above!</p>
    2. Build and run again: 
       Keep in mind that in order to run again we first have to stop and remove the running conatiner and then run it again
       
       $ docker build -t getting-started .
       $ docker ps
       $ docker stop <the-container-id>
       $ docker rm <the-container-id>
       $ docker run -dp 127.0.0.1:3000:3000 getting-started
# Sharing the app 
    It is like sharing in git hub repo
    https://docs.docker.com/get-started/04_sharing_app/ -> follow the documentation here.

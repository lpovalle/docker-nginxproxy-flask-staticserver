# docker-nginxproxy-flask-staticserver
------------------------------------------

Example of how to deploy a nginx container working as a localy reverse proxy that redirects to two diferents containers. The first is running a simple Flask app in a python image, this app save all the information in a redis container. The second is running a nginx server, serving static content. 

### Cool Diagram:
-------------------------------------------

<p align="center">
  <img src="img/docker-intermediate.png"/>
</p>

## How it works:
------------------------------------------

Docker compose is a tool that let you run multiple containers at once, every container can be different from the others. Its only necesary one `docker-compose.yml` file.

In the `docker-compose.yml` file you must specifie what images and what options for the containers are going to run.

Example:

```

version: "3.3"
services:
  database:
    image: "redis:alpine"

```
What is going to do, is create a container named database from an redis:alpine image.

## How to use it:
------------------------------------------

Run the following command in the bash: 

`docker-compose up -d `

(If you don't want to run it detached, write the command without the ` -d`.)

Go to the web browser and write `localhost/app1` for the static webpage or `localhost/app2` for the flask app.

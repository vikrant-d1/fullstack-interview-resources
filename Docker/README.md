# Docker

## 1.Run node app in local enviroment with docker container

``` docker
FROM node:14
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
EXPOSE 3000
CMD [ "node", "app.js" ]
```

### Docker commands to need to run docker project locally.

* It documents that a process in the container will expose this port. But you still need to then actually expose the port with -p when running docker run. So technically, -p is the only required part when it comes to listening on a port. Still, it is a best practice to also add EXPOSE in the Dockerfile to document this behavior.

1. docker build .
2. docker run -p 3000:3000 de223hhue2
> In last this is the docker image id this id you get if you run docker buid command

#### List of running container
3. docker ps 

#### Stop running container

4. docker stop _________ 
 > In blank space write the running container name you get the running container name from "docker ps" command

## 2. To find built in image in docker 

  [Docker hub](https://hub.docker.com)

  * You can run built in image in docker e.g. "docker run node" here node is built in command.
  * Find the docker procesing image [docker ps -a]
  * changing the flag to interactive mode node image [docker run -it node] 
     

     

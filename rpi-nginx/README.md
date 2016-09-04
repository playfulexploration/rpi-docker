# rpi-nginx-nw

This is work in progress.

Todo:
* Add conf file
* 

## Build
Build for local use:
```bash
 docker build -t playfulexploration/rpi-nginx-nw .
```

Or build for upload:
```bash
 docker build -t playfulexploration/rpi-nginx-nw:latest -t playfulexploration/rpi-nginx-nw:v0.1 .
```

## Try it out
Ensure the docker network exists.
```bash
 docker network create nw
```
Start the container, use -d option to run it in the background.
```bash
 docker run -d --restart=always --name nginx-nw -h nginx-nw --net=nw -p 80:80 -p 443:443 playfulexploration/rpi-nginx-nw
```
Find the container's IP.
```bash
 docker inspect nginx | grep IPAddress
```
Send a web request, it should return some html.
```bash
 curl http://localhost
```
Attach to the container to make changes:
```bash
 sudo docker exec -it nginx-nw bash
```

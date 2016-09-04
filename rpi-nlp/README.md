# rpi-nlp

A Dockerfile that spans Stanford's Natural Languge Processing service as a web server.

## Status ##
Not working.  RPI3 runs out of memory on server startup.

## Next steps ##
Wait for RPI4 or change of memory requirements.

## Build
Build for local use:
```bash
 docker build -t playfulexploration/rpi-nlp .
```

Or build for upload:
```bash
 docker build -t playfulexploration/rpi-nlp:latest -t playfulexploration/rpi-nlp:v0.1 .
```

## Try it out
Ensure the docker network exists.
```bash
 docker network create nw
```
Start the container, use -d option to run it in the background.
```bash
 docker run -d --restart=always --name nlp -h nlp --net=nw -p 80:80 -p 443:443 playfulexploration/rpi-nlp
```
Send a web request, it should return some html.
```bash
 curl --data 'text=Hello world!' http://localhost:8080
```

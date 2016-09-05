# rpi-volumes

This container aims to have access to the data volumes of all other containers in order manage their configuration and backups. 

## Build
Build for local use:
```bash
 docker build -t playfulexploration/rpi-volumes .
```

Or build for upload:
```bash
 docker build -t playfulexploration/rpi-volumes:latest -t playfulexploration/rpi-volumes:v0.1 .
```

## Try it out
Ensure the docker network exists.
```bash
 docker network create nw
```
Start the container.  Use --rm option to self-destruct on exit.  Use the --volumes-from option to map the volumes of one or more target containers to manage.
```bash
 docker run -it --rm --name volumes -h volumes --net=nw --volumes-from nginx playfulexploration/rpi-volumes
```


# rpi-docker
Docker setup and Dockerfiles for the Raspberry PI.

# Status
| Dockerfile                   | Status        | Detail  |
| ---------------------------- | ------------- | -----   |
| [rpi-nginx](rpi-nginx)       | In progress   | Starts nginx as docker service.  Still needs conf file.  |
| [rpi-influxdb](rpi-influxdb) | In progress   | Starts influxdb as docker service.  Needs configuration for ease of use. |
| [rpi-nlp](rpi-nlp)           | On hold       | Starts Stanford's Natural Language Processor as Web Service.  Runs out of memory on RPI3.  |
| [rpi-grafana](rpi-grafana)   | Not started   | Starts influxdb as docker service.  Needs configuration for ease of use. |

# Goal
Create an extensible nginx configuration for docker based plug-in webservices.

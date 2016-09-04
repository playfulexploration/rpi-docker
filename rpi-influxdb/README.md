rpi-influxdb
This project is based on [tutum/influxdb](https://github.com/tutumcloud/influxdb) 

InfluxDB image

Usage
-----

To get a docker image with influxdb version 0.13.0 running simply clone the repository:

    wget https://github.com/regexing/rpi-influxdb/archive/master.zip -O temp.zip && unzip temp.zip && rm temp.zip

Then run docker build:

    docker build -t regexing/rpi-influxdb rpi-influxdb-master/ && rm -rf rpi-influxdb-master

Start your image binding the external ports `8083` and `8086` in all interfaces to your container. Ports `8090` and `8099` are only used for clustering and should not be exposed to the internet.

    docker run --name influxdb -d -p 8083:8083 -p 8086:8086 -e PRE_CREATE_DB="db1" regexing/rpi-influxdb

Open your browse to access `localhost:8083` to configure InfluxDB. The default credential is `root:root`. Please change it as soon as possible.

You can use RESTful API to talk to InfluxDB on port `8086`

    

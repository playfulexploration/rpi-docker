FROM resin/rpi-raspbian:wheezy
MAINTAINER Peter Hartmann

RUN apt-get update && apt-get install curl

# Install InfluxDB
ENV INFLUXDB_VERSION 0.13.0
#ADD src/influxdb_${INFLUXDB_VERSION}_armhf.deb /tmp/influxdb_${INFLUXDB_VERSION}_armhf.dep
ADD https://dl.influxdata.com/influxdb/releases/influxdb_${INFLUXDB_VERSION}_armhf.deb /tmp/influxdb_${INFLUXDB_VERSION}_armhf.dep
RUN dpkg -i /tmp/influxdb_${INFLUXDB_VERSION}_armhf.dep && \
  rm /tmp/influxdb_${INFLUXDB_VERSION}_armhf.dep && \
  rm -rf /var/lib/apt/lists/*

ADD src/config.toml /config/config.toml
ADD src/run.sh /run.sh
RUN chmod +x /*.sh

ENV PRE_CREATE_DB=**None** SSL_SUPPORT=**False** SSL_CERT=**None**

# Admin server, HTTP API
EXPOSE 8083 8086

# Raft port (for clustering, don't expose publicly!)
#EXPOSE 8090

# Protobuf port (for clustering, don't expose publicly!)
#EXPOSE 8099

VOLUME ["/data"]

CMD ["/run.sh"]

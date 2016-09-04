#FROM resin/rpi-raspbian:wheezy
FROM dordoka/rpi-java8
#FROM webskin/docker-debian-java-8-oracle

MAINTAINER Peter Hartmann

#install CoreNLP, see also: https://github.com/nlohmann/StanfordCoreNLPXMLServer

RUN apt-get update
RUN apt-get install -y unzip ant
WORKDIR /root
ADD https://codeload.github.com/nlohmann/StanfordCoreNLPXMLServer/zip/master tmp.zip
RUN unzip tmp.zip && rm tmp.zip
RUN mv StanfordCoreNLPXMLServer-master StanfordCoreNLPXMLServer
WORKDIR /root/StanfordCoreNLPXMLServer
RUN ant libs && ant jar
RUN rm -rf /var/lib/apt/lists/*

# Define mountable directories.
# VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/etc/nginx/conf.d", "/var/log/nginx", "/var/www/html"]

# Define working directory.
WORKDIR /root/StanfordCoreNLPXMLServer

# Define default command.
#CMD ["ant run"]

# Expose ports.
EXPOSE 80 443

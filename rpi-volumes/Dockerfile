FROM resin/rpi-raspbian:wheezy
MAINTAINER Peter Hartmann

RUN apt-get update
RUN apt-get install -y nano
RUN rm -rf /var/lib/apt/lists/*

# Define mountable directories.
VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/etc/nginx/conf.d", "/var/log/nginx", "/var/www/html"]

# Define working directory.
WORKDIR /root

# Define default command.
CMD ["bash"]

FROM resin/rpi-raspbian:wheezy
MAINTAINER Peter Hartmann

RUN apt-get update
RUN apt-get install -y nano
RUN rm -rf /var/lib/apt/lists/*

# Define working directory.
WORKDIR /root

# Define default command.
CMD ["bash"]

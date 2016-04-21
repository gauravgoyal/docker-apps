FROM phusion/baseimage

# Specifying the maintainer for this image.
MAINTAINER Gaurav Goyal "gaurav.goyal@innoraft.com"

# Configuration for SSH Keys

# Open SSH server configurations
ENV AUTHORIZED_KEYS **None**
RUN mkdir -p /etc/my_init.d && rm -f /etc/service/sshd/down
ADD ssh_config.sh /etc/my_init.d/ssh_config.sh

# Update sources list for multiverse too.
RUN echo "deb http://mirrors.digitalocean.com/ubuntu trusty main multiverse" >> /etc/apt/sources.list && \
    echo "deb http://mirrors.digitalocean.com/ubuntu trusty-updates main multiverse" >>  /etc/apt/sources.list && \
    echo "deb http://security.ubuntu.com/ubuntu trusty-security main multiverse" >> /etc/apt/sources.list

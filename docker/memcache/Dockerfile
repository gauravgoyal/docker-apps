FROM innoraft/ubuntu

MAINTAINER Gaurav Goyal "gaurav.goyal@innroaft.com"

RUN apt-get update && \
    apt-get install -y memcached

EXPOSE 11211

CMD ["/usr/bin/memcached", "-u", "memcache", "-v"]

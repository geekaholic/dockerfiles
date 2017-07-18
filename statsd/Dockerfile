FROM debian:latest
MAINTAINER Bud Siddhisena "bud@geekaholic.org"

# Example to create a container
# docker run --rm -p 8125:8125/udp -it --name 'statsd' geekaholic/statsd

# To test
# echo echo "foo:1|c" | nc -w 1 -u 127.0.0.1 8125

ENV BUILD_DATE 20170717
EXPOSE 8125/udp

# Lets always use bash
RUN ln -sf /bin/bash /bin/sh

# Install dependencies
RUN apt-get update && apt-get install -y \
    git-core vim nodejs \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir /app
WORKDIR /app

# Setup statsd
RUN git clone https://github.com/etsy/statsd.git

COPY devConfig.js /app/statsd

WORKDIR /app/statsd

CMD /usr/bin/nodejs stats.js devConfig.js


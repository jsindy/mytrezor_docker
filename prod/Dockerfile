#mytrezor docker image
#Joshua Sindy 2015

FROM ubuntu:14.04

EXPOSE 8000

ENV HOME /root

WORKDIR /root

RUN apt-get update; apt-get install -y git npm nodejs-legacy vim
RUN adduser --disabled-password --gecos "" mytrezor
RUN npm install -g grunt-cli bower
RUN echo '127.0.0.1	localhost.mytrezor.com >> /etc/hosts'

ENV HOME /home/mytrezor
WORKDIR /home/mytrezor
USER mytrezor

RUN cd /home/mytrezor/
RUN git clone https://github.com/trezor/webwallet.git
RUN git checkout stable
WORKDIR /home/mytrezor/webwallet
RUN git submodule update --recursive --init
RUN npm config set prefix /usr/local
RUN bower install
RUN npm install
RUN mv app/scripts/config.sample.js app/scripts/config.js
RUN grunt build
RUN cp -r app/data dist/data
RUN sed 's/https:\/\/mytrezor.com/https:\/\/localhost.mytrezor.com/g' /home/mytrezor/webwallet/app/scripts/config.js
USER mytrezor

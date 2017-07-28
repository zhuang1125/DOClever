FROM node:boron
MAINTAINER liwei liwei@wayearn.com

RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak

COPY ./sources.list /etc/apt/

RUN apt-get update \
  && apt-get install -yqq supervisor mongodb 

RUN mkdir -p /var/log/supervisor

RUN git clone https://github.com/sx1989827/DOClever.git /root/DOClever

RUN mkdir -p /data/db

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
EXPOSE 10000

COPY ./entrypoint.sh /

ENTRYPOINT [/entrypoint.sh]

# Docker file with jdk
# docker build . -t jdk
#    To start:
#    docker run  -p 8888:8888 jdk
#
#
FROM debian:latest
# use bash
RUN rm /bin/sh && ln -s /bin/bash /bin/sh
# Avoid triggering apt-get dialogs (which may lead to errors). See:
# https://stackoverflow.com/questions/25019183/docker-java7-install-fail
ENV DEBIAN_FRONTEND noninteractive

ENV JAVA_HOME=/usr/lib/jvm/adoptopenjdk-14-hotspot-amd64


RUN apt-get update ; apt-get -y upgrade ; apt-get -y autoclean
RUN apt-get -y install wget gnupg2
RUN wget -qO - https://adoptopenjdk.jfrog.io/adoptopenjdk/api/gpg/key/public | apt-key add -
RUN apt-get -y install software-properties-common
RUN add-apt-repository --yes https://adoptopenjdk.jfrog.io/adoptopenjdk/deb/
RUN apt-get update && apt-get install -y adoptopenjdk-14-hotspot

CMD java --version

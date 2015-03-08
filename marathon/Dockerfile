# Pull base image
FROM ubuntu

MAINTAINER Archs sun@archs.tk

# Add the repository
RUN echo "deb http://mirrors.sohu.com/ubuntu/ trusty main restricted universe" >> /etc/apt/sources.list
RUN sudo apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF

RUN	echo "deb http://repos.mesosphere.io/ubuntu trusty main" >> /etc/apt/sources.list

# update source
RUN sudo apt-get -y update

# Install packages
# RUN sudo apt-get -y install openjdk-7-jre-headless
RUN sudo apt-get -y install zookeeper mesos marathon chronos

# start the service
RUN service zookeeper start
RUN service marathon start

# Expose ports.
EXPOSE 5050 8080 2181 3888

# Define default command.
# ENTRYPOINT ["/opt/mongodb-linux-x86_64-ubuntu1404-3.0.0/bin/mongod"]
# ENTRYPOINT ["/opt/https"]
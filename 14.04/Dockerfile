#
# Ubuntu-16.04 Docker Container
#
# This image can be used to build binaries that are compatible with Ubuntu 16.04
#

FROM ubuntu:14.04
MAINTAINER micheli.andrea@gmail.com

ENV DEBIAN_FRONTEND noninteractive

# Install Dev tools
RUN apt-get update && apt-get install -y gcc make cmake tar g++ libxml2-dev flex bison libreadline-dev swig python-dev nano wget libboost-all-dev libgmp-dev openjdk-7-jdk

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64

CMD /bin/bash
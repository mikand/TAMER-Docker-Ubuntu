#
# Ubuntu-18.04 Docker Container
#
# This image can be used to build binaries that are compatible with Ubuntu 16.04
#

FROM ubuntu:20.04
MAINTAINER micheli.andrea@gmail.com

ENV DEBIAN_FRONTEND noninteractive

# Install Dev tools
RUN apt-get update && apt-get install -y gcc make cmake tar g++ libxml2-dev doxygen flex bison libreadline-dev swig python3-dev nano wget libboost-all-dev libgmp-dev openjdk-11-jdk libgtest-dev lcov graphviz texlive unzip git gcovr

# GTest
RUN mkdir /tmp/gtest-build && cd /tmp/gtest-build && cmake -DCMAKE_BUILD_TYPE=RELEASE /usr/src/gtest/ && make && mv lib/libg* /usr/lib/ && cd / && rm -rf /tmp/gtest-build

# Install MathSAT in /mathsat
RUN cd /tmp && \
    wget --no-check-certificate https://optimathsat.disi.unitn.it/releases/optimathsat-1.7.3/optimathsat-1.7.3-linux-64-bit.tar.gz -O optimathsat-1.7.3-linux-64-bit.tar.gz && \
    tar xfz optimathsat-1.7.3-linux-64-bit.tar.gz && \
    mv optimathsat-1.7.3-linux-64-bit /mathsat && \
    rm -rf optimathsat-1.7.3-linux-64-bit.tar.gz

ENV JAVA_HOME /usr/lib/jvm/java-11-openjdk-amd64

CMD /bin/bash
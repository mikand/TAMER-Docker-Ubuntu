#
# RHEL6-Compatible Docker Container
#
# This image can be used to build binaries that are compatible with
# the environment on the FBK RHEL6 machines.

FROM centos:6
MAINTAINER micheli.andrea@gmail.eu

# Install Dev tools
RUN yum install -y gcc make cmake tar gcc-c++ patch git \
                   libxml2-devel flex bison gmp-static \
                   readline-devel swig python-devel hg \
                   java-1.8.0-openjdk-headless.x86_64 \
                   java-1.8.0-openjdk-devel nano wget \
                   lcov gtest

RUN rpm --import http://ftp.scientificlinux.org/linux/scientific/5x/x86_64/RPM-GPG-KEYs/RPM-GPG-KEY-cern && \
    wget -O /etc/yum.repos.d/slc6-devtoolset.repo http://linuxsoft.cern.ch/cern/devtoolset/slc6-devtoolset.repo

RUN yum install -y devtoolset-2-gcc devtoolset-2-gcc-c++ devtoolset-2-binutils

RUN scl enable devtoolset-2 bash

# Install MathSAT in /mathsat
RUN cd /tmp && \
    wget --no-check-certificate http://mathsat.fbk.eu/download.php?file=mathsat-5.3.13-linux-x86_64.tar.gz -O mathsat-5.3.13-linux-x86_64.tar.gz && \
    tar xfz mathsat-5.3.13-linux-x86_64.tar.gz && \
    mv mathsat-5.3.13-linux-x86_64 /mathsat && \
    rm -rf mathsat-5.3.13-linux-x86_64.tar.gz

# Install boost in /boost
RUN cd /tmp && \
    wget --no-check-certificate https://sourceforge.net/projects/boost/files/boost/1.62.0/boost_1_62_0.tar.bz2/download -O boost.tar.bz2 && \
    tar xfj boost.tar.bz2 && \
    mv boost_1_62_0 /boost && \
    rm -rf boost.tar.bz2

CMD /bin/bash

#
# Kore-Compatible Docker Container with TAMER dependencies
#

FROM scientificlinux/sl:7
MAINTAINER micheli.andrea@gmail.com

RUN yum update -y

# Install Dev tools
RUN yum install -y gcc make cmake tar gcc-c++ patch git \
                   libxml2-devel flex bison gmp-static \
                   readline-devel swig python-devel hg \
                   java-1.8.0-openjdk-devel wget \
                   boost-devel

# GTest
RUN cd /tmp && wget https://github.com/google/googletest/archive/release-1.8.1.tar.gz && tar xfz release-1.8.1.tar.gz
RUN mkdir /tmp/gtest-build && cd /tmp/gtest-build && cmake -DCMAKE_BUILD_TYPE=RELEASE /tmp/googletest-release-1.8.1/googletest && make && mv libg* /usr/lib64/ && cp -r /tmp/googletest-release-1.8.1/googletest/include/gtest /usr/include && cd / && rm -rf /tmp/gtest-build

# Install MathSAT in /mathsat
RUN cd /tmp && \
    wget --no-check-certificate http://mathsat.fbk.eu/download.php?file=mathsat-5.3.13-linux-x86_64.tar.gz -O mathsat-5.3.13-linux-x86_64.tar.gz && \
    tar xfz mathsat-5.3.13-linux-x86_64.tar.gz && \
    mv mathsat-5.3.13-linux-x86_64 /mathsat && \
    rm -rf mathsat-5.3.13-linux-x86_64.tar.gz

ENV JAVA_HOME /usr/lib/jvm/java-1.8.0

VOLUME ["/data"]

CMD "/bin/bash"
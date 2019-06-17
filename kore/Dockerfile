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
                   java-1.8.0-openjdk-headless.x86_64 \
                   boost-devel

VOLUME ["/data"]

CMD "/data/extra/docker/kore/compile_tamer.sh"
#
# Ubuntu-18.04 Docker Container
#
# This image can be used to build binaries that are compatible with Ubuntu 16.04
#

FROM ubuntu:20.04
MAINTAINER micheli.andrea@gmail.com

ENV DEBIAN_FRONTEND noninteractive

# Install Dev tools
RUN apt-get update && apt-get install -y clang-format python3

CMD /bin/bash
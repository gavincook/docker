# This one will download the lastest jdk when build
FROM ubuntu:14.04

# Last modified at 2015-07-06
MAINTAINER gavincook <swbyzx@gmail.com>

RUN sed -i "s/archive\.ubuntu\.com/mirrors\.163\.com/g" /etc/apt/sources.list && \
  apt-get update

# Install jdk1.8
RUN \
  sudo DEBIAN_FRONTEND=noninteractive apt-get install software-properties-common -y && \
  sudo add-apt-repository ppa:webupd8team/java && \
  sudo apt-get update && \ 
  echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  echo debconf shared/accepted-oracle-license-v1-1 seen true | debconf-set-selections && \
  sudo DEBIAN_FRONTEND=noninteractive apt-get install oracle-java8-installer -y
 
CMD ["/bin/bash"]

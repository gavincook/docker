FROM ubuntu:14.04

# last modified at 2015-08-28
MAINTAINER gavincook <swbyzx@gmail.com>

RUN sed -i "s/archive\.ubuntu\.com/mirrors\.163\.com/g" /etc/apt/sources.list && \
  apt-get update

ENV PATH /usr/local/program/jdk/bin:$PATH
ENV JAVA_HOME /usr/local/program/jdk

# first you must download the jdk from internet into current directory, then rename it to jdk.tar.gz
COPY jdk.tar.gz jdk.tar.gz

# Install jdk1.8
RUN \
  tar -xvf jdk*.tar.gz &&\
  mkdir -p /usr/local/program && \
  mv jdk*/ /usr/local/program/jdk

CMD ["/bin/bash"]


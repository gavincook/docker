FROM ubuntu:14.04

# last modified at 2015-07-06
MAINTAINER gavincook <swbyzx@gmail.com>

RUN sed -i "s/archive\.ubuntu\.com/mirrors\.163\.com/g" /etc/apt/sources.list && \
  apt-get update

ENV PATH /usr/local/program/jdk1.8.0_45/bin:$PATH
ENV JAVA_HOME /usr/local/program/jdk1.8.0_45

# first you must download the jdk from internet into current directory, then rename it to jdk8u45.tar.gz
COPY jdk8u45.tar.gz jdk8u45.tar.gz

# Install jdk1.8
RUN \
  tar -xvf jdk8u*.tar.gz &&\
  mkdir /etc/local && \
  mv jdk1.8* /usr/local/program/jdk1.8.0_45

CMD ["/bin/bash"]


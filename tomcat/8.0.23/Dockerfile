FROM jdk:1.8.0_45


# Last modified at 2015-07-06
MAINTAINER gavincook <swbyzx@gmail.com>

# Set the ubuntu mirror to the 163 for faster speed

RUN sed -i "s/archive\.ubuntu\.com/mirrors\.163\.com/g" /etc/apt/sources.list && \
  apt-get update


# Install tomcat8

RUN \
  DEBIAN_FRONTEND=noninteractive apt-get install -y wget && \
  wget http://mirrors.hust.edu.cn/apache/tomcat/tomcat-8/v8.0.23/bin/apache-tomcat-8.0.23.tar.gz && \
  tar -xvf apache-tomcat*.tar.gz &&\
  rm apache-tomcat*.tar.gz && \
  mkdir -p /usr/local/program && \
  mv apache-tomcat* /usr/local/program/tomcat/

EXPOSE 8080

CMD ["./usr/local/program/tomcat/bin/catalina.sh","run"]


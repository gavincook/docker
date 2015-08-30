FROM jdk:1.8


# Last modified at 2015-07-06
MAINTAINER gavincook <swbyzx@gmail.com>

ENV CATALINA_HOME /usr/local/program/tomcat

COPY scripts /scripts

RUN chmod +x /scripts/start

RUN \
  DEBIAN_FRONTEND=noninteractive apt-get install -y wget && \
  wget http://apache.fayea.com/tomcat/tomcat-8/v8.0.26/bin/apache-tomcat-8.0.26.tar.gz && \
  tar -xvf apache-tomcat*.tar.gz &&\
  rm apache-tomcat*.tar.gz && \
  mkdir -p /usr/local/program && \
  mv apache-tomcat* /usr/local/program/tomcat 
  

VOLUME ["/usr/local/program/tomcat/logs"]

EXPOSE 8080

CMD ["/scripts/start"]


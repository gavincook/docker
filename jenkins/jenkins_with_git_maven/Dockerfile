FROM jdk:1.8

# Last modified at 2015-08-31
MAINTAINER gavincook <swbyzx@gmail.com>

COPY jenkins.war /jenkins.war

RUN \ 
  DEBIAN_FRONTEND=noninteractive apt-get install -y git && \
  apt-get install -y maven

ENTRYPOINT ["java","-jar","/jenkins.war"]

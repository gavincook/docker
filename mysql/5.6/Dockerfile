FROM ubuntu:14.04

# Last modified at 2015-07-06
MAINTAINER gavincook <swbyzx@gmail.com>

RUN sed -i "s/archive\.ubuntu\.com/mirrors\.163\.com/g" /etc/apt/sources.list && \
	apt-get update
# The exit 0 is used to solve the error: invoke-rc.d: policy-rc.d denied execution of start.
RUN \
  echo "#!bin/bash \n exit 0" > /usr/sbin/policy-rc.d && \
  DEBIAN_FRONTEND=noninteractive apt-get install -y mysql-server-5.6

COPY scripts /scripts
RUN chmod +x /scripts/start

COPY my.cnf my.cnf
RUN mv my.cnf /etc/mysql/my.cnf

EXPOSE 3306

VOLUME ["/var/lib/mysql"]

ENTRYPOINT ["/scripts/start"]


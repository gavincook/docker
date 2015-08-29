FROM ubuntu:14.04

# Last modified at 2015-07-05
MAINTAINER gavincook <swbyzx@gmail.com>
 
RUN sed -i "s/archive\.ubuntu\.com/mirrors\.163\.com/g" /etc/apt/sources.list && \
  apt-get update

COPY nginx-1.8.0.tar.gz nginx-1.8.0.tar.gz
COPY nginx.conf nginx.conf
COPY start start

RUN chmod +x start
# Install nginx 1.8.0
# first install the dependency ones for nginx
RUN \
  DEBIAN_FRONTEND=noninteractive apt-get install -y make gcc zlib1g zlib1g-dev libpcre3 libpcre3-dev &&\ 
  tar -xvzf nginx*.tar.gz &&\
  rm nginx*.gz && \ 
  cd nginx-1.8.0 && \
  ./configure --prefix=/usr/local/program/nginx && \
  make && \
  make install &&\
  cp -r /usr/local/program/nginx/conf /usr/local/program/nginx/conf-backup
 

EXPOSE 80 443

VOLUME ["/usr/local/program/nginx/html","/user/local/program/nginx/conf","/usr/local/program/nginx/logs"]

CMD ["/start"]

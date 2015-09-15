FROM nginx:1.8.0

# Last modified at 2015-09-15
MAINTAINER gavincook <swbyzx@gmail.com>
 
RUN sed -i "s/mirrors\.163\.com/mirrors\.aliyun\.com/g" /etc/apt/sources.list && \
  apt-get update

COPY www.conf www.conf
COPY start start
COPY nginx.conf nginx.conf
COPY app/ /app
RUN chmod +x start && \
    chmod +x /app/init.sh

RUN \
  DEBIAN_FRONTEND=noninteractive apt-get install -y php5 php5-fpm php5-gd php5-ldap php-pear php5-mysql php5-mcrypt php5-xcache php5-xmlrpc &&\ 
  rm -r /etc/php5/fpm/pool.d/* && \
  mv www.conf /etc/php5/fpm/pool.d/ && \
  echo "<?php phpinfo(); ?>" > /app/info.php   

EXPOSE 80 443

CMD ["/start"]

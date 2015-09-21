# php-fpm in docker

This image is based on the `nginx:1.8.0`, which is build from [docker file](https://git.oschina.net/gavincook/docker/tree/master/nginx/1.8.0). There contains some files:

* [nginx.conf](https://git.oschina.net/gavincook/docker/blob/master/php-fpm/nginx.conf): this one is the nginx configuration, there expose prot 80 and 443. and use fast-cgi to forward requests to php-fpm

* [www.conf](https://git.oschina.net/gavincook/docker/blob/master/php-fpm/www.conf): www part for php-fpm, would listen on prot 9000.

* [start](https://git.oschina.net/gavincook/docker/blob/master/php-fpm/start) : This is the main entrypoint for current php-fpm image. It would start two progress: php-fpm and nginx

* [init.sh](https://git.oschina.net/gavincook/docker/blob/master/php-fpm/app/init.sh): In the app folder, you can place your own php web project. The `init.sh` used to custom commands need to executed for real app project.

### build example

`docker build -t php-fpm:5 .`

### run example

`docker run -d -p 80:80 -p 443:443 php-fpm:5`

### test 

`curl 127.0.0.1/info.php`
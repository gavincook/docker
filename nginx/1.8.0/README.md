### Nginx 1.8.0 in docker

Nginx 1.8.0 will installed under `/usr/local/program/nginx` folder. It use the `nginx.conf` as config file, users can replace it with theirs' own config file when build the Nginx image.
It export port `80` to host pc. 

* build command: `docker build -t nginx:1.8.0 .`

* run command example: `docker run -d -v /data/nginx:/usr/local/program/nginx/html -p 80:80 nginx:1.8.0`

* there has three volumes, the `conf`, `html` and the `logs` folder. it allow to edit the configure file in the host machine, once it changed, can use command :`docker kill -s HUP <container_name>` to reload the configure file, the same effect as `./nginx -s reload`

_refrerence:_ : https://www.nginx.com/blog/deploying-nginx-nginx-plus-docker/ and http://nginx.org/en/docs/control.html

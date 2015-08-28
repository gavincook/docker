### mysql 5.6 in docker

* there support custom username and password for mysql:DB_USER for username(default admin) and DB_PWD for password(default 123456)

* volume for mysql data is : /var/lib/mysql

* export port is : 3306

* run mysql example: `docker run -d -p 3306:3306 -v /data/mysql:/var/lib/mysql -e DB_USER=root -e DB_PWD=rootpwd mysql:5.6`, this command would start a mysql with user:root,  password:rootpwd on port 3306

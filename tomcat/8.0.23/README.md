### tomcat 8.x in docker

tomcat will installed under `/usr/local/program/tomcat`, there support add manage user for tomcat, only need pass the parameters:`TOMCAT_USER` and `TOMCAT_PWD` for the manage user infomation.

* expose port: 8080, 443
* volume: /usr/local/program/tomcat/logs
* build command: `docker build -t tomcat:8 .`
* run command example: `docker run -d -e TOMCAT_USER=admin -e TOMCAT_PWD=123456 -P tomcat:8`, this one would start a tomcat with a manager(username:admin,password:123456), and a random port
* this tomcat support remote management, like deploy war file remotely: `curl -X PUT -T /path/warfile http://username:password@tomcatserverpath/manager/text/deploy?path=/xxx\&update=true`, see [doc](https://tomcat.apache.org/tomcat-8.0-doc/manager-howto.html) for details.


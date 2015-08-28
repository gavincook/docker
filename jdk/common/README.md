### java environment in docker
_this Dockerfile suitable for all java version_

* first there must download the jdk tar file, rename it to jdk.tar.gz and put it into the same folder which the Dockerfile placed

* run command `docker build -t jdk:1.8 .`

* then use `docker images`, there should has an image named jdk with tag 1.8

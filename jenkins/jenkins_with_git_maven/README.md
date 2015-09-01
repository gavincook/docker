# jenkins(with git and maven) in docker

This image procide git, maven and jenkins, the git and maven are generally needed in ci operation.

* first you need download the jenkins.war file into current folder,[link](http://mirrors.jenkins-ci.org/war/latest/jenkins.war), and rename to `jenkins.war` if it with other names.

* build command: `docker run -t jenkins .`

* there allow you pass startup arguments to jenkins, for example, use --httpPort to config the listen port. the run command in this case like: `docker run -d -p 80:80 jenkins --httpPort=80`. this command will config the jenkins httpport to 80 instead of default port 8080.Take a look [here](https://wiki.jenkins-ci.org/display/JENKINS/Starting+and+Accessing+Jenkins) for what arguments can applied to jenkins

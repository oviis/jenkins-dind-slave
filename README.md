## This Docker image combine remote JNLP Jenkins slave and Docker inception, to build inside docker more docker images dynamicaly

inspired by and credits to:<br>
[JNLP Slave](https://hub.docker.com/r/jenkinsci/jnlp-slave/)<br>
[DockerInDocker docker/dind](https://hub.docker.com/_/docker/)

A [Jenkins](https://jenkins-ci.org) slave using JNLP to establish connection.

See [Jenkins Distributed builds](https://wiki.jenkins-ci.org/display/JENKINS/Distributed+builds) for more info.

See [Docker inception](https://github.com/jpetazzo/dind)

## Running

To run a Docker container, it is important to run it in **privileged** mode, like:

    docker run --privileged oviis/jenkins-dind-slave:v1 -url http://jenkins-server:port <secret> <slave name>

optional environment variables:

* `JENKINS_URL`: url for the Jenkins server, can be used as a replacement to `-url` option, or to set alternate jenkins URL
* `JENKINS_TUNNEL`: (`HOST:PORT`) connect to this slave host and port instead of Jenkins server, assuming this one do route TCP traffic to Jenkins master. Useful when when Jenkins runs behind a load balancer, reverse proxy, etc.

## image Stack

the Image have been build on the docker alpine base <br>
and have a openjdk8-jre inside <br>
and a docker daemon started as a jenkins user


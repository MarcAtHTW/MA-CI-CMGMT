#FROM msahib/jenkins-build-master:v1
FROM msahib/jenkins-build-master:0.0.169_2019-04-21
USER root

COPY sources.list /etc/apt/sources.list

RUN apt-get -o Acquire::Check-Valid-Until=false update

RUN apt-get update && apt-get upgrade -y && apt-get install -y \
maven \
apt-transport-https \
vim \
libtiff-tools 

RUN apt-get upgrade -y \
systemd \
libc6 \
curl \
libtiff5 \
util-linux \
python \
openjdk-8-jdk \
wget \
vim

RUN apt-get purge -y && apt-get autoremove -y \
mercurial  

#COPY glibc-source_2.24-11+deb9u4_all.deb /tmp/
#RUN dpkg -i /tmp/glibc-source_2.24-11+deb9u4_all.deb

RUN dpkg --purge libssl1.0.2:amd64

RUN apt-get dist-upgrade -y

USER jenkins

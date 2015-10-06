FROM profideo/php54-apache-node:unstable

MAINTAINER Alban Duval <aduval@profideo.com>

RUN echo 'deb http://ftp.debian.org/debian/ wheezy-backports main' > /etc/apt/sources.list.d/libreoffice.list
RUN apt-get update
RUN apt-get -t wheezy-backports install libreoffice -qq -u -y

RUN apt-get install unoconv -qq -u -y 
RUN apt-get install bzip2 -qq -u -y 

# Install client php mongodb
RUN apt-get -t wheezy-backports install php5-mongo -qq -u -y

FROM profideo/php55-apache-node:unstable

MAINTAINER Alban Duval <aduval@profideo.com>

# update apt
RUN apt-get update

# Install imagemagick
RUN apt-get -y install php5-imagick
RUN test -e '/etc/init.d/apache2' && command service 'apache2' 'force-reload'

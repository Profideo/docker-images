FROM profideo/php55-apache:unstable

MAINTAINER Alban Duval <aduval@profideo.com>

# @see https://github.com/joyent/node/wiki/installing-node.js-via-package-manager
# @see https://deb.nodesource.com/setup
RUN echo 'deb https://deb.nodesource.com/node wheezy main' > /etc/apt/sources.list.d/nodesource.list
RUN echo 'deb-src https://deb.nodesource.com/node wheezy main' >> /etc/apt/sources.list.d/nodesource.list
RUN apt-get install -y apt-transport-https
RUN curl -s https://deb.nodesource.com/gpgkey/nodesource.gpg.key | apt-key add -
RUN apt-get update
RUN apt-get install nodejs npm -qq -u -y
RUN mkdir -p /home/profideo/.npm
RUN chown -R profideo:profideo /home/profideo/.npm
RUN npm install -g less
RUN npm install -g bower
RUN npm cache clean
RUN npm update -g

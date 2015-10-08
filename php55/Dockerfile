FROM profideo/debian-wheezy:unstable

MAINTAINER Alban Duval <aduval@profideo.com>

# php5 from dotdeb (wheezy => php5.5)
RUN echo "deb http://packages.dotdeb.org wheezy-php55 all" > /etc/apt/sources.list.d/php.list
RUN echo "deb-src http://packages.dotdeb.org wheezy-php55 all" >> /etc/apt/sources.list.d/php.list

#update apt-get with the new repo
#get the public key from the repo
RUN wget http://www.dotdeb.org/dotdeb.gpg
RUN apt-key add dotdeb.gpg
RUN apt-get update

#install php5.5
RUN apt-get install -y php-http php-http-request php-net-socket php-net-url php-pear php5-cli php5-common php5-curl php5-dev php5-gd php5-intl php5-ldap php5-mcrypt php5-mysql php5-xsl

# Install PHP HttpRequest
RUN apt-get install -y libcurl4-openssl-dev make
RUN echo "\n"|pecl install pecl_http-1.7.6
#RUN echo "extension=http.so" > /etc/php5/conf.d/20-http.ini

# Install PHP OLE for obsExcel
RUN pear install channel://pear.php.net/OLE-1.0.0RC2

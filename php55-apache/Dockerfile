FROM profideo/php55:unstable

MAINTAINER Alban Duval <aduval@profideo.com>

ENV DEBIAN_FRONTEND noninteractive
ENV HOME /root
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

RUN apt-get update

# install apache
RUN apt-get install -y apache2
RUN apt-get install -y libapache2-mod-php5
RUN apt-get install mysql-server -qq -u -y
RUN apt-get install mysql-client -qq -u -y
RUN /etc/init.d/mysql restart
RUN a2enmod rewrite
#RUN chown www-data:www-data /var/lock/apache2 -R 
RUN echo "umask 002" >> /etc/apache2/envvars
RUN a2enmod php5
RUN service apache2 restart
# Add user profideo to group www-data
RUN usermod -a -G www-data profideo

EXPOSE 80

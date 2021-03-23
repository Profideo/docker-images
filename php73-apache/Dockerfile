FROM profideo/php-7.3-fpm

# Install apt-transport-https
RUN apt-get update && apt-get install -y apt-transport-https

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install PHP extensions
RUN apt-get update && apt-get install -y libzip-dev libpng-dev
RUN docker-php-ext-install pdo pdo_mysql zip sockets gd

# Install ClamAV
RUN apt-get update && apt-get install -y clamav clamav-freshclam clamav-daemon

# Install nodejs
RUN apt-get install -y software-properties-common
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get install -y --force-yes nodejs

# Supervisor
COPY files/supervisord.conf /etc/supervisor/conf.d/supervisord.conf
CMD ["/usr/bin/supervisord"]

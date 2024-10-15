FROM php:8.1-apache
#RUN apt-get update && apt-get upgrade -y
#RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
#RUN docker-php-ext-install zip && docker-php-ext-enable zip
RUN apt update && apt install -y libpng-dev libfreetype6-dev libpng-dev libjpeg-dev libpng-dev libmagickwand-dev libc-client-dev libkrb5-dev --no-install-recommends && rm -rf /var/lib/apt/lists/*
RUN a2enmod rewrite
RUN mkdir -p /usr/src/php/ext/imagick && curl -fsSL https://github.com/Imagick/imagick/archive/06116aa24b76edaf6b1693198f79e6c295eda8a9.tar.gz | tar xvz -C "/usr/src/php/ext/imagick" --strip 1
RUN docker-php-ext-configure gd --with-jpeg=/usr/include/ --with-freetype=/usr/include/
RUN docker-php-ext-configure imap --with-kerberos --with-imap-ssl
RUN docker-php-ext-install bz2 exif gd imagick imap mysqli opcache pdo_mysql
COPY ./app.ini /usr/local/etc/php/conf.d/app.ini

FROM php:7.4-fpm

ENV DOCKERIZE_VERSION v0.6.1

RUN apt-get update \
    && apt-get install -y zlib1g-dev libzip-dev libfreetype6-dev libjpeg62-turbo-dev libpng-dev libonig-dev wget \
    && docker-php-ext-install zip exif gd pdo_mysql mysqli mbstring sockets \
    && docker-php-ext-configure gd --with-freetype --with-jpeg  \
    && docker-php-ext-install -j$(nproc) gd \
    && curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer \
    && apt-get install -y zip unzip git \
    && wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

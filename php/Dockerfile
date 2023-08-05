FROM php:fpm-alpine

RUN apk update && apk add --no-cache tzdata

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions && install-php-extensions \
    gd \
    mcrypt \
    mysqli \
    pdo_mysql \
    memcached \
    imagick \
    zip \
    opcache xdebug

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

ADD ./conf.d/php-fpm.conf /usr/local/etc/php-fpm.conf
ADD ./conf.d/php.ini /usr/local/etc/php/php.ini

ADD ./conf.d/xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
ADD ./conf.d/memcached.ini /usr/local/etc/php/conf.d/xx-php-ext-memcached.ini
ADD ./conf.d/opcache.ini /usr/local/etc/php/conf.d/docker-php-ext-opcache.ini

RUN rm /var/cache/apk/*

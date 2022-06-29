FROM php:8.0-fpm-alpine

LABEL maintainer="AGL Sistemas <contato@aglsistemas.com.br>"

ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_PROCESS_TIMEOUT 900
ENV COMPOSER_DISABLE_XDEBUG_WARN=1

ENV XDEBUG_IDEKEY xdebug
ENV XDEBUG_CLIENT_HOST 127.0.0.1
ENV XDEBUG_CLIENT_PORT 9003
ENV XDEBUG_MODE off
ENV XDEBUG_START_WITH_REQUEST off

RUN apk update
RUN apk add wget

RUN apk add --no-cache --virtual .phpize_deps $PHPIZE_DEPS

RUN pecl install xdebug
RUN docker-php-ext-enable xdebug

RUN docker-php-ext-install pdo
RUN docker-php-ext-install pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

RUN composer self-update
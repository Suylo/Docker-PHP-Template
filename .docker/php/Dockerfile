# version php
FROM php:7.4-apache
RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"
RUN cp /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled/

RUN apt update \
    && apt install -y zlib1g-dev g++ git zip libzip-dev libicu-dev zip default-libmysqlclient-dev \
    && docker-php-ext-install pdo pdo_mysql intl \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug
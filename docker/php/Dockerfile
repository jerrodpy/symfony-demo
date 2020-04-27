FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
        libzip-dev \
        zip \
        wget \
	&& docker-php-ext-configure zip \
	&& docker-php-ext-install zip \
	&& docker-php-ext-install mysqli

RUN  pecl install xdebug \
    &&  docker-php-ext-enable xdebug

COPY php.ini /usr/local/etc/php/php.ini
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html
FROM php:7.4-fpm-buster
SHELL ["/bin/bash", "-oeux", "pipefail", "-c"]

ENV COMPOSER_ALLOW_SUPERUSER=1 \
    COMPOSER_HOME=/composer

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN apt-get update && \
    apt-get -y install git unzip libzip-dev libicu-dev libonig-dev vim && \
    git clone https://github.com/phpredis/phpredis.git /usr/src/php/ext/redis && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    pecl install xdebug && \
    docker-php-ext-install intl pdo_mysql zip bcmath redis && \
    docker-php-ext-enable xdebug

COPY ./php.ini /usr/local/etc/php/php.ini
COPY ./xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

WORKDIR /work

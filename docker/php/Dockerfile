FROM php:8.0-apache

RUN apt-get update \
    && apt-get install -y zlib1g-dev libzip-dev zip unzip mariadb-client \
    && docker-php-ext-install zip pdo_mysql \
    && a2enmod rewrite

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs

COPY --from=composer /usr/bin/composer /usr/bin/composer
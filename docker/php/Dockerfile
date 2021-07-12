FROM php:8.0-fpm-alpine

COPY ./docker/php/php.ini /usr/local/etc/php/php.ini

COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

RUN apk add --update --no-cache \
    nodejs \
    npm \
    git \
    zip \
    unzip \
    vim \
    postgresql-dev \
    postgresql-client \
    && docker-php-ext-install pdo_pgsql bcmath \
    && npm install vue@next \
    && npm install -g @vue/cli

WORKDIR /var/www/html

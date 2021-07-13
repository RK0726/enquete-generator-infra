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
    && npm update \
    && npm install vue@next -D \
    && npm install vue-loader@next -D \
    && npm install vue-router@next -D \
    && npm install @vue/compiler-sfc -D \
    && npm install @types/webpack-env typescript ts-loader -D \
    && npm install -g @vue/cli

WORKDIR /var/www/html

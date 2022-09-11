FROM php:8.1-apache

RUN apt-get update && apt-get install -y \
    zip \
    git \
    zlib1g-dev \
    libpng-dev \
    libbz2-dev

RUN rm -rf /var/lib/apt/lists/*

ENV APACHE_DOCUMENT_ROOT=/var/www/html/public

COPY ./kaitos-api /usr/local/apache2/htdocs

WORKDIR /usr/local/apache2/htdocs

RUN docker-php-ext-install \
    pdo_mysql \
    gd \
    bcmath \
    mbstring

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN composer install
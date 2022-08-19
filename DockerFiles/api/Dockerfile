FROM php:8.1-fpm

# Dependências
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

# Limpa cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Adiciona extensões do php
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# Adiciona composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Define diretório atual
WORKDIR /var/www

# Adiciona usuário
RUN useradd -ms /bin/bash devUser

# Utiliza usuário criado
USER devUser
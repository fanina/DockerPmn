FROM composer:2.0 as composer

FROM php:7.4-fpm-buster

RUN docker-php-ext-install pdo_mysql

RUN pecl install apcu

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
    curl \
    libpng-dev \
    libonig-dev \
    libicu-dev \
    libmemcached-dev \
    libz-dev \
    libpq-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libssl-dev \
    libzip-dev \
    zip \
    unzip \
    libmcrypt-dev \
    libxml2-dev \
    libbz2-dev \
    libjpeg62-turbo-dev \
    git \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*


RUN docker-php-ext-install zip
RUN docker-php-ext-enable apcu

RUN mkdir /var/www/app
WORKDIR /var/www/app
#COPY --chown=1000:1000 apps/my-symfony-app /usr/src/my-symfony-app

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
&& composer --version

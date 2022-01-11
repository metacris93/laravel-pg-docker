FROM php:7.3-apache

ARG user
ARG uid

RUN apt update \
  && apt install -y \
      git \
      curl \
      g++ \
      libicu-dev \
      libpq-dev \
      libzip-dev \
      zip \
      zlib1g-dev \
  && docker-php-ext-install \
      intl \
      opcache \
      pdo \
      pdo_pgsql \
      pgsql \
      mbstring \
      exif \
      bcmath

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN useradd -G www-data,root -u $uid -d /home/$user $user
RUN mkdir -p /home/$user/.composer && \
    chown -R $user:$user /home/$user

# RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/laravel_docker
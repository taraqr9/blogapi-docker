FROM php:8.0-fpm-alpine

ARG SERVER_ENVIRONMENT


# Add Build Dependencies
RUN apk update && apk add --no-cache  \
    libzip-dev \
    libmcrypt-dev \
    libjpeg-turbo-dev \
    libjpeg-turbo \
    jpeg-dev \
    libpng-dev \
    libxml2-dev \
    bzip2-dev \
    libwebp-dev \
    zip \
    jpegoptim \
    pngquant \
    optipng \
    icu-dev \
    freetype-dev \
    zlib-dev \
    curl-dev \
    imap-dev \
    git \
    vim

RUN docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp
RUN docker-php-ext-configure imap

# Configure & Install Extension
RUN docker-php-ext-configure \
    opcache --enable-opcache &&\
    docker-php-ext-configure zip && \
    docker-php-ext-install -j "$(nproc)" \
    opcache \
    pdo \
    pdo_mysql \
    sockets

# Add Composer
RUN curl -sS https://getcomposer.org/installer | \
php -- --install-dir=/usr/bin/ --filename=composer
#RUN composer install  --no-interaction --optimize-autoloader --no-dev --prefer-dist

# Setup Working Dir
WORKDIR /var/www
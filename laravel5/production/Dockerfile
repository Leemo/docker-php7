FROM php:7.1-fpm-alpine

Maintainer Alexey Popov <leemo-studio.net>

ENV IMAGICK_VERSION 3.4.2

RUN apk add --no-cache \
    zip \
    unzip \
    mysql-client \
	freetype-dev \
	libjpeg-turbo-dev \
	libpng-dev

# Imagick 
RUN apk add --no-cache imagemagick-dev libtool autoconf gcc g++ make \
    && pecl install imagick-$IMAGICK_VERSION \
    && echo "extension=imagick.so" > /usr/local/etc/php/conf.d/ext-imagick.ini \
    && apk del libtool autoconf gcc g++ make

# extensions
RUN docker-php-ext-install bz2 exif gd opcache pdo_mysql zip

EXPOSE 9000
CMD ["entrypoint.sh"]

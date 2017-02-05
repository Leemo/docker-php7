FROM php:7.1-fpm-alpine

Maintainer Alexey Popov <leemo-studio.net>

RUN apk add --update --no-cache \
	bzip2-dev \
	freetype-dev \
	libjpeg-turbo-dev \
	libmcrypt-dev \
	libpng-dev \
	libxml2-dev \
	mysql-client \
	openssl \
	unzip \
	zip

RUN docker-php-ext-install \
	bz2 \
	gd \
	json \
	mcrypt \
	mbstring \
	opcache \
	pdo \
	pdo_mysql \
	tokenizer \
	xml \
	zip

RUN apk add --update --no-cache autoconf g++ imagemagick-dev libtool make \
    && pecl install imagick \
    && docker-php-ext-enable imagick \
    && apk del autoconf g++ libtool make

RUN curl -sS https://getcomposer.org/installer | php \
	&& mv composer.phar /usr/local/bin/composer \
	&& rm -rf /var/cache/apk/*

EXPOSE 9000
CMD ["php-fpm"]

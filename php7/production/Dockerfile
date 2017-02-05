FROM php:7.1-fpm-alpine

Maintainer Alexey Popov <leemo-studio.net>

ENV IMAGICK_VERSION 3.4.2

RUN apk add --update --no-cache \
	bzip2-dev \
	freetype-dev \
	git \
	libjpeg-turbo-dev \
	libmcrypt-dev \
	libpng-dev \
	mysql-client \
	unzip \
	zip

RUN docker-php-ext-install \
	bz2 \
	exif \
	gd \
	json \
	mcrypt \
	mbstring \
	opcache \
	openssl \
	pdo \
	pdo_mysql \
	phar
	tokenizer \
	xml \
	zip

RUN apk add --no-cache --virtual .imagick-build-dependencies \
    libtool \
	autoconf \
	git \
	gcc \
	g++ \
	make \
	imagemagick-dev \
    && apk add --virtual .imagick-runtime-dependencies \
    imagemagick \

    && IMAGICK_TAG="3.4.2" \
    && git clone -o ${IMAGICK_TAG} --depth 1 https://github.com/mkoppanen/imagick.git /tmp/imagick \
    && cd /tmp/imagick \

    && phpize \
    && ./configure \
    && make \
    && make install \

    && echo "extension=imagick.so" > /usr/local/etc/php/conf.d/ext-imagick.ini \

    && apk del .imagick-build-dependencies

RUN curl -sS https://getcomposer.org/installer | php \
	&& mv composer.phar /usr/local/bin/composer \
	&& rm -rf /var/cache/apk/*

EXPOSE 9000
CMD ["entrypoint.sh"]

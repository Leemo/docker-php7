FROM alpine:edge

Maintainer Alexey Popov <leemo-studio.net>

ENV TIMEZONE UTC
ENV PHP_MEMORY_LIMIT 512M
ENV MAX_UPLOAD 50M
ENV PHP_MAX_FILE_UPLOAD 200
ENV PHP_MAX_POST 100M

# PHP7 and packages
RUN apk add --update --no-cache \
	curl \
	php7 \
	php7-bz2 \
	php7-curl \
	php7-fpm \
	php7-gd \
	php7-json \
	php7-mbstring \
	php7-mcrypt \
	php7-opcache \
	php7-openssl \
	php7-pdo \
	php7-pdo_mysql \
	php7-phar \
	php7-xml \
	php7-xmlreader \
	php7-zip \
	php7-zlib \
	--repository http://dl-cdn.alpinelinux.org/alpine/edge/community/

RUN ln -s /usr/bin/php7 /usr/bin/php \
	&& ln -s /usr/bin/php7 /usr/bin/php \
	&& ln -s /usr/bin/php-config7 /usr/bin/php-config \
	&& ln -s /usr/bin/phpize7 /usr/bin/phpize \
	&& curl -sS https://getcomposer.org/installer | php \
	&& mv composer.phar /usr/local/bin/composer

RUN rm -rf /var/cache/apk/*

EXPOSE 9000

WORKDIR /var/www
VOLUME /var/www

ENTRYPOINT ["php-fpm7"]

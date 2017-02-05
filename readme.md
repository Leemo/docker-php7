# PHP7 docker images

[![Docker Automated build](https://img.shields.io/docker/automated/leemo/php7.svg?style=flat-square)](https://hub.docker.com/r/leemo/php7/)
[![Docker Pulls](https://img.shields.io/docker/pulls/leemo/php7.svg?style=flat-square)](https://hub.docker.com/r/leemo/php7/)
[![Docker Stars](https://img.shields.io/docker/stars/leemo/php7.svg?style=flat-square)](https://hub.docker.com/r/leemo/php7/)

* `leemo/php7:latest` - for production
* `leemo/php7:staging` - for staging and build

## Modules
**leemo/php7:latest** contains:
* php-bz2
* php-gd
* php-json
* php-mcrypt
* php-mbstring
* php-opcache
* php-pdo
* php-pdo_mysql
* php-tokenizer
* php-xml
* php-zip
* composer

**leemo/php7:staging** contains:
Soon...

## Install [docker-compose](https://docs.docker.com/compose/)
See: https://docs.docker.com/compose/install/
```
$ curl -L "https://github.com/docker/compose/releases/download/1.10.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ chmod +x /usr/local/bin/docker-compose
```

## Example configs
See in:
* docker-compose.yml
* nginx-domain.conf

## Run
```
$ docker-compose run
```

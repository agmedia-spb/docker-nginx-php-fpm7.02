# docker nginx php-fpm 7.0 git node.js npm gulp-cli

## Overview

This is a Dockerfile/image to build a container ubuntu:16.04 for nginx and php-fpm, with php modules, Node.js npm gulp-cli, and also git.


[![Docker](https://img.shields.io/badge/Docker%20Tag-latest-green.svg)]()
[![Github](https://img.shields.io/badge/GitHub%20Release%20-Master%20Branch-green.svg)]()

[![Nginx](https://img.shields.io/badge/nginx-1.10.0-blue.svg)]()
[![php](https://img.shields.io/badge/php-7.0.15-blue.svg)]()
[![git](https://img.shields.io/badge/git-2.7.4-blue.svg)]()
[![nodejs](https://img.shields.io/badge/nodejs-4.2.6-blue.svg)]()
[![npm](https://img.shields.io/badge/npm-3.5.2-blue.svg)]()
[![gulp](https://img.shields.io/badge/gulp-1.3.0-blue.svg)]()


List PHP modules:
```
[PHP Modules]
amqp bcmath calendar Core ctype curl date  dom exif fileinfo filter ftp gd gettext gmp hash
iconv intl json ldap libxml mbstring mcrypt mongodb mysqli mysqlnd openssl pcntl pcre PDO
pdo_mysql Phar posix readline Reflection session shmop SimpleXML soap sockets SPL standard 
sysvmsg sysvsem sysvshm tokenizer wddx xml xmlreader xmlrpc xmlwriter xsl Zend OPcache zip zlib
[Zend Modules]
Zend OPcache
```
Addition:

`git mc postfix`

## Links 
[Docker hub](https://hub.docker.com/r/agmedia/docker-nginx-php-fpm7.0/)

## Quick Start

To pull from docker hub:

`docker pull agmedia/docker-nginx-php-fpm7.0`

### Running
##### Simple run project 
```     
docker run -d -p 8080:80 \
      --rm \
      -v $(pwd)/www/:/var/www/html/ \
      --name test-docker \
      agmedia/docker-nginx-php-fpm7.0
```

##### Run project with nginx and php-fpm configs
```     
docker run -d -p 8080:80 \
      --rm \
      -v $(pwd)/www/:/var/www/html/ \
      -v $(pwd)/php-fpm/php.ini:/etc/php/7.0/fpm/php.ini \
      -v $(pwd)/php-fpm/php-fpm.conf:/etc/php/7.0/fpm/php-fpm.conf \
      -v $(pwd)/nginx/default.conf:/etc/nginx/conf.d/default.conf \
      -v $(pwd)/nginx/nginx.conf/:/etc/nginx/nginx.conf/ \
      --name test-docker \
      agmedia/docker-nginx-php-fpm7.0
```

##### Enter container bash

`docker exec -it test-docker /bin/bash`
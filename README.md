[![][image-layers-status]][img-layers]

# Drone build container for the Symfony2 development framework

A build container intended for running builds for the [Symfony2][symfony]
framework using the [Drone][drone] continuous integration platform.

The image is based on [Alpine Linux][alpine] version 3.2, and builds upon their
[minimal docker image][docker-alpine].

## Features

The container provides command line `php` and the `php-fpm` daemon, along with
the following PHP modules:

* bcmath
* ctype
* ctype
* curl
* json
* mcrypt
* mysql
* opcache
* openssl
* pdo
* pdo_mysql
* pdo_sqlite
* sqlite3
* zlib

In addition [Composer][composer] is available to bootstrap your [Symfony2][symfony]
applications.

## Usage

This container is intended to be used as build image in Drone, as shown in
the following example:

```yaml
build:
  image: danielsreichenbach/symfony:full
  commands:
    - composer install
```

## Known issues

Currently it is not possible to run [PhantomJS][phantomjs] inside Alpine based
containers due to there being no build compatible with Alpine's musl libc.

:cry:


[symfony]:        http://symfony.com/
[composer]:       https://getcomposer.org/
[phantomjs]:      http://phantomjs.org/

[drone]:          https://github.com/drone/drone/
[alpine]:         http://alpinelinux.org/
[docker-alpine]:  https://hub.docker.com/r/gliderlabs/alpine/

[img-layers]:          https://imagelayers.io/?images=danielsreichenbach/symfony:latest "Get your own badge on imagelayers.io"
[image-layers-status]: https://badge.imagelayers.io/danielsreichenbach/symfony:latest.svg

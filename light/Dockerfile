FROM gliderlabs/alpine:3.3
MAINTAINER Daniel S. Reichenbach <daniel@kogitoapp.com>

RUN set -ex \
	&& apk add --update \
    && apk add curl git \
    && apk add mariadb-client \
    && apk add php-cli php-bcmath php-bz2 php-ctype php-curl php-dom php-gd php-iconv php-intl php-json php-mcrypt php-opcache php-openssl php-pcntl php-pdo php-pdo_mysql php-pdo_sqlite php-phar php-posix php-xml php-zlib  \
    && rm -rf /var/cache/apk/*

# Add support for Composer
RUN set -ex \
	&& curl -LsS https://getcomposer.org/composer.phar -o /usr/bin/composer
RUN set -ex \
	&& chmod +x /usr/bin/composer

# Add support for Deployer
RUN set -ex \
	&& curl -LsS http://deployer.org/deployer.phar -o /usr/bin/dep
RUN set -ex \
	&& chmod +x /usr/bin/dep

# Create directories required to run
RUN set -ex \
	&& mkdir -p /var/www

VOLUME ["/var/www"]

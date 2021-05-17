FROM php:8.0.5-fpm-alpine

RUN apk update; \
    apk upgrade; \
    apk add --no-cache icu-dev autoconf g++ make


COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/

# these are slow steps so makes sense to have sepearte RUN for each extension
# so on the failure we don't need to run the previous step agin.

# https://github.com/mlocati/docker-php-extension-installer
RUN install-php-extensions gd
RUN install-php-extensions intl
RUN install-php-extensions mbstring
RUN install-php-extensions pdo_mysql
RUN install-php-extensions tidy
RUN install-php-extensions xdebug

RUN install-php-extensions @composer


COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

COPY ./conf.d/php.ini /usr/local/etc/php/conf.d

RUN apk add nodejs

WORKDIR  /srv



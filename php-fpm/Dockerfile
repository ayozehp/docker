FROM php:7.3-fpm
WORKDIR /app

RUN apt-get update && apt-get install -y librabbitmq-dev \
    && pecl install xdebug-2.7.2 \
    && pecl install redis-4.3.0 \
    && pecl install amqp-1.9.4 \
    && pecl install apcu-5.1.17 \
    && docker-php-ext-install -j$(nproc) \
        bcmath \
        opcache \
	&& docker-php-ext-enable \
        xdebug \
        opcache \
        redis \
        amqp \
        apcu

COPY ./etc/ /usr/local/etc/php/
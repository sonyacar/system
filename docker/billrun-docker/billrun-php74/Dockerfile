from php:7.4-fpm
# https://github.com/netroby/docker-php-fpm/blob/master/Dockerfile

RUN apt-get update && apt-get install -y \
        wkhtmltopdf \
    && pecl install yaf \
    && pecl install mongodb \
    && pecl install xdebug-3.0.4 \
    && docker-php-ext-enable yaf mongodb xdebug \
    && docker-php-ext-install pcntl bcmath

COPY php-fpm.conf /usr/local/etc/
COPY php.ini /usr/local/etc/php/
COPY xdebug.ini /usr/local/etc/php/conf.d/
CMD ["php-fpm"]

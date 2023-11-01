FROM php:8.1-fpm-alpine

RUN apk update && apk add \
    build-base \
    vim \
    bash \
    curl

RUN curl -sSLf \
            -o /usr/local/bin/install-php-extensions \
            https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions

RUN chmod +x /usr/local/bin/install-php-extensions
RUN install-php-extensions \
    pdo \
    pdo_pgsql



RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html

CMD ["php-fpm"]



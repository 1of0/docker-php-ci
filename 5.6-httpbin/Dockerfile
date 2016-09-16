FROM php:5.6-cli

RUN apt-get update
RUN apt-get install -yyy git unzip curl python-pip gunicorn
RUN pip install httpbin

RUN curl --location --output /usr/local/bin/phpunit https://phar.phpunit.de/phpunit.phar && chmod +x /usr/local/bin/phpunit
RUN curl --location --output /usr/local/bin/composer https://getcomposer.org/composer.phar && chmod +x /usr/local/bin/composer

RUN echo "date.timezone = UTC" >> /usr/local/etc/php/conf.d/test.ini

RUN pecl install xdebug
RUN docker-php-ext-enable xdebug 
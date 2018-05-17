FROM php:5.6-cli

RUN apt update
RUN apt install -yyy git unzip curl libffi-dev python-pip python-dev gunicorn
RUN pip install --upgrade cffi
RUN pip install httpbin

RUN curl --location --output /usr/local/bin/phpunit https://phar.phpunit.de/phpunit.phar && chmod +x /usr/local/bin/phpunit
RUN curl --location --output /usr/local/bin/composer https://getcomposer.org/composer.phar && chmod +x /usr/local/bin/composer

RUN echo "date.timezone = UTC" >> /usr/local/etc/php/conf.d/test.ini

RUN pecl install xdebug-2.5.5
RUN docker-php-ext-enable xdebug 
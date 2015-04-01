FROM php:5.5

WORKDIR /tmp

RUN apt-get update && apt-get install -y socat build-essential libicu-dev git curl libcurl4-openssl-dev zlib1g-dev && rm -rf /var/lib/apt/lists/*
RUN curl https://pecl.php.net/get/mongo-1.5.8.tgz > /tmp/mongo.tgz
RUN tar -xpzf mongo.tgz
RUN mv /tmp/mongo-1.5.8 /usr/src/php/ext

RUN docker-php-ext-install sockets
RUN docker-php-ext-install curl
RUN docker-php-ext-install zip
RUN docker-php-ext-install mbstring
RUN docker-php-ext-install intl
RUN docker-php-ext-install mongo-1.5.8

WORKDIR /usr/local/bin
RUN curl -sS https://getcomposer.org/installer | php
RUN chmod a+x composer.phar
RUN mv composer.phar composer

CMD ["php", "-v"]

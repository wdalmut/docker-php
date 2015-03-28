FROM php:5.6

RUN apt-get update && apt-get install -y git curl libcurl4-openssl-dev zlib1g-dev && rm -rf /var/lib/apt/lists/*
RUN docker-php-ext-install sockets
RUN docker-php-ext-install curl
RUN docker-php-ext-install zip
RUN docker-php-ext-install mbstring

WORKDIR /usr/local/bin
RUN curl -sS https://getcomposer.org/installer | php
RUN chmod a+x composer.phar
RUN mv composer.phar composer

CMD ["php", "-v"]

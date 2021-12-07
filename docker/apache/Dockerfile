FROM php:7-apache
 
# PHP extensions
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
		libonig-dev \
	&& apt-get install -y libicu-dev \
    && docker-php-ext-install -j$(nproc) intl mbstring pdo_mysql tokenizer iconv mysqli gd \
	&& pecl install mcrypt \
	&& docker-php-ext-enable mcrypt \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN a2enmod rewrite
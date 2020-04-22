FROM php:7.2-apache

RUN apt-get update && apt-get install -y \
	g++ \
	git \
	libicu-dev \
	libxml2-dev \
	mariadb-client \
	unzip \
	vim \
	zlib1g-dev \
 && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-configure soap \
	&& docker-php-ext-install soap \
	&& docker-php-ext-configure intl \
	&& docker-php-ext-install intl \
	&& docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli

RUN a2enmod rewrite

WORKDIR /var/www/html

RUN git clone https://github.com/tkrebs/ep3-bs .

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
	&& php composer-setup.php \
	&& rm composer-setup.php \
	&& php composer.phar install

RUN set -ex; \
	chown -R www-data:www-data /var/www/html

# uncomment the email notifications
RUN find module -type f -name 'NotificationListener.php' -exec sed -ie '/$events->attach/s/^/#/' '{}' +
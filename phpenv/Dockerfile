FROM php:8.2-fpm-bullseye
RUN apt-get update && \
    apt-get install -y libpq-dev libonig-dev zlib1g zlib1g-dev libzip-dev \
    libcurl4-openssl-dev libxml2-dev libpng-dev libjpeg-dev cmake libfreetype6-dev \
    libfontconfig1-dev xclip libjpeg62-turbo-dev && \ 
    docker-php-ext-install pdo_mysql mysqli intl && \
    docker-php-ext-install zip dom simplexml iconv fileinfo mbstring curl&&\
    docker-php-ext-configure gd --with-freetype --with-jpeg && \
    docker-php-ext-install -j$(nproc) gd 


    WORKDIR /var/www/html

#
# WindowsでファイルマウントができないためPHP.INIのコピー
#
COPY php.ini /usr/local/etc/php/php.ini
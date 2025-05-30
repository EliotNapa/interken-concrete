FROM php:8.4
RUN apt-get update && \
    apt-get install -y libpq-dev libonig-dev zlib1g zlib1g-dev libpng-dev libjpeg-dev cmake libfreetype6-dev libzlib-dev libfontconfig1-dev xclip libjpeg62-turbo-dev libpng12-dev && \ 
    docker-php-ext-install pdo_mysql mysqli && \
    docker-php-ext-install zip dom simplexml iconv fileinfo mbstring curl&&\
    docker-php-ext-configure gd --with-freetype --with-jpeg && \
    docker-php-ext-install -j$(nproc) gd 


    WORKDIR /var/www/html

#
# WindowsでファイルマウントができないためPHP.INIのコピー
#
COPY php.ini /usr/local/etc/php/php.ini
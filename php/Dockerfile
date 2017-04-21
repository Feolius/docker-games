FROM php:5.6-apache

RUN docker-php-ext-install pdo && docker-php-ext-enable pdo
RUN docker-php-ext-install pdo_mysql && docker-php-ext-enable pdo_mysql

RUN pecl install xdebug
ENV XDEBUGINI_PATH=/usr/local/etc/php/conf.d/xdebug.ini
RUN echo "zend_extension="`find /usr/local/lib/php/extensions/ -iname 'xdebug.so'` > $XDEBUGINI_PATH
COPY xdebug.ini /tmp/xdebug.ini
RUN cat /tmp/xdebug.ini >> $XDEBUGINI_PATH
    

ADD src /var/www/html
FROM crunchgeek/php-fpm:7.2
RUN apt-get update && apt-get install -y \
    && docker-php-ext-enable opcache \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install gd
# Copy extensions had downloaded
COPY ./pkg/redis.tgz /home/redis.tgz

# Install PECL extensions (Redis)
RUN pecl install /home/redis.tgz && echo "extension=redis.so" > /usr/local/etc/php/conf.d/redis.ini

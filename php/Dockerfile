FROM php:8.3-fpm

RUN apt-get update \
    && apt-get install -y \
        curl \
        libcurl4-openssl-dev \
        libfreetype-dev \
        libzip-dev \
        zip \
        libxml2-dev \
        optipng \
        unzip \
        nano

# Install extensions
RUN docker-php-ext-install \
    bcmath \
    curl \
    exif \
    gd \
    intl \
    opcache \
    pcntl \
    pdo_mysql \
    soap \
    xml \
    zip

# Install pecl extensions
RUN pecl install -o -f xdebug \
    &&  docker-php-ext-enable xdebug \
    &&  rm -rf /tmp/pear

# Install composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Clear cache to reduce image size
RUN apt-get -y autoremove && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Add any extra dependencies here...

CMD ["php-fpm"]
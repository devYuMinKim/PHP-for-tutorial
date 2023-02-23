FROM php:8.1.16-apache

# Enable mod_rewrite
RUN a2enmod rewrite

# Set the working directory
WORKDIR /var/www/html

# Copy the application code to the container
COPY . /var/www/html

# Install dependencies
RUN apt-get update \
    && apt-get install -y \
        libzip-dev \
    && docker-php-ext-install pdo_mysql zip \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

# Expose port 80
EXPOSE 80
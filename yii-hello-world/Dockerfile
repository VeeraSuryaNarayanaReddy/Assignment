FROM php:7.4-apache

# Enable mod_rewrite
RUN a2enmod rewrite

# Copy app code to Apache's root
COPY ./web /var/www/html/

# Set permissions
RUN chown -R www-data:www-data /var/www/html




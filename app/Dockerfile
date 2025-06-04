FROM yiisoftware/yii2-php:7.4-apache

# Set working directory
WORKDIR /app

# Copy only composer files first (for layer caching)
COPY composer.json composer.lock ./

# Install PHP dependencies
RUN composer install

# Copy rest of the app source code
COPY . .

# Set proper permissions (optional but recommended)
RUN chown -R www-data:www-data /app && chmod -R 755 /app

# Expose Apache port
EXPOSE 80

# Start Apache
CMD ["apache2-foreground"]

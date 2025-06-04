FROM yiisoftware/yii2-php:7.4-apache

# Set working directory
WORKDIR /app

# Copy composer files and install dev dependencies
COPY composer.json composer.lock ./

# Install PHP dependencies including dev tools like yii2-debug
RUN composer install --no-interaction --prefer-dist

# Copy rest of the application code
COPY . .

# Permissions (optional)
RUN chown -R www-data:www-data /app && chmod -R 755 /app

# Expose Apache port
EXPOSE 80

# Start Apache
CMD ["apache2-foreground"]

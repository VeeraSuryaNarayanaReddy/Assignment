FROM yiisoftware/yii2-php:7.4-apache

# Set working directory
WORKDIR /app

# Copy composer files first
COPY composer.json composer.lock ./

# Install dependencies including dev packages (important!)
RUN composer install --no-interaction --prefer-dist --dev


# Copy remaining source code
COPY . .

# Set permissions
RUN composer install --no-interaction --prefer-dist \
 && ls -la vendor/yiisoft/yii2-debug

# Expose Apache port
EXPOSE 80

# Start Apache
CMD ["apache2-foreground"]

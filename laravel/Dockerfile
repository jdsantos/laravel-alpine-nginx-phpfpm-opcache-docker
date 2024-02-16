FROM php:8.3-fpm-alpine

# Set working directory
WORKDIR /opt/laravel

# Install additional packages
RUN apk --no-cache add \
    nginx \
    supervisor \
    && docker-php-ext-enable opcache

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Copy Nginx configuration
COPY conf.d/nginx/default.conf /etc/nginx/nginx.conf

# Copy PHP configuration
COPY conf.d/php-fpm/php-fpm.conf /usr/local/etc/php-fpm.d/www.conf

COPY conf.d/php/php.ini /usr/local/etc/php/conf.d/php.ini

COPY conf.d/php/opcache.ini /usr/local/etc/php/conf.d/opcache.ini

# Copy Supervisor configuration
COPY conf.d/supervisor/supervisord.conf /etc/supervisord.conf

# Copy Laravel application files
COPY . /opt/laravel

# Set up permissions
RUN chown -R www-data:www-data /opt/laravel \
    && chmod -R 755 /opt/laravel/storage

# Scheduler setup

# Create a log file
RUN touch /var/log/cron.log

# Add cron job directly to crontab
RUN echo "* * * * * /usr/local/bin/php /opt/laravel/artisan schedule:run >> /var/log/cron.log 2>&1" | crontab -

# Expose ports
EXPOSE 80

ADD entrypoint.sh /root/entrypoint.sh

ENTRYPOINT ["/root/entrypoint.sh"]

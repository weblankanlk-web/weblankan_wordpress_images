
FROM wordpress:php8.3

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    zlib1g-dev \
    libzip-dev \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    libssl-dev \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip

# Install PhpRedis
RUN pecl install redis \
    && docker-php-ext-enable redis

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

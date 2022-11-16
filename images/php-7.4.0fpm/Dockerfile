FROM php:7.4.0-fpm
RUN apt update;
RUN apt install -y --no-install-recommends libjpeg-dev libpng-dev libfreetype6-dev libcurl4-openssl-dev openssl libc-client-dev libkrb5-dev libicu-dev ffmpegthumbnailer libzip-dev
RUN docker-php-ext-configure gd --with-jpeg=/usr/include;
RUN docker-php-ext-install -j "$(nproc)" curl exif gd iconv intl json mysqli opcache zip
RUN { \
	echo 'opcache.memory_consumption=128'; \
	echo 'opcache.interned_strings_buffer=8'; \
	echo 'opcache.max_accelerated_files=4000'; \
	echo 'opcache.revalidate_freq=2'; \
	echo 'opcache.fast_shutdown=1'; \
	} > /usr/local/etc/php/conf.d/opcache-recommended.ini

CMD ["php-fpm"]
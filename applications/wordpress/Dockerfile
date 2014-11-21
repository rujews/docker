FROM rujews/nginx-php:latest
MAINTAINER Max Schaefer <max@excloo.com>
ENV VERSION 4.0.1
RUN mkdir -p /data/nginx/www/wordpress
WORKDIR /data/nginx/www/wordpress
RUN wget -O - "https://github.com/rujews/wordpress/raw/master/wordpress-${VERSION}-zh_CN.tar.gz" | tar --strip-components=1 -x -z

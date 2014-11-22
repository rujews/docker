FROM rujews/nginx-php:latest
MAINTAINER Max Schaefer <max@excloo.com>
ENV VERSION 4.0.1
RUN mkdir -p /config/res/wordpress
WORKDIR  /config/res/wordpress
RUN wget -O - "https://github.com/rujews/mirror/raw/master/wordpress/wordpress-${VERSION}-zh_CN.tar.gz" | tar --strip-components=1 -x -z
ADD config /config

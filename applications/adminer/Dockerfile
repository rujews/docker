FROM rujews/nginx-php:latest
MAINTAINER Max Schaefer <max@excloo.com>
ENV VERSION 4.1.0
RUN mkdir -p /data/nginx/www/adminer
RUN wget -O /data/nginx/www/adminer/index.php "http://www.sourceforge.net/projects/adminer/files/Adminer/Adminer ${VERSION}/adminer-${VERSION}.php/download"
RUN wget -O /data/nginx/www/adminer/adminer.css "https://raw.githubusercontent.com/vrana/adminer/master/designs/pokorny/adminer.css"

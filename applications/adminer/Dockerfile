FROM rujews/nginx-php:latest
MAINTAINER Max Schaefer <max@excloo.com>
ENV VERSION 4.1.0
RUN mkdir -p /config/res/adminer
RUN wget -O /config/res/adminer/index.php "http://www.sourceforge.net/projects/adminer/files/Adminer/Adminer ${VERSION}/adminer-${VERSION}.php/download"
RUN wget -O /config/res/adminer/adminer.css "https://raw.githubusercontent.com/vrana/adminer/master/designs/pokorny/adminer.css"
ADD config /config

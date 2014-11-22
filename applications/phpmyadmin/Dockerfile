FROM rujews/nginx-php:latest
MAINTAINER Max Schaefer <max@excloo.com>
ENV VERSION 4.2.12
RUN mkdir -p /config/res/phpmyadmin
WORKDIR  /config/res/phpmyadmin
RUN wget -O - "https://github.com/rujews/mirror/raw/master/phpmyadmin/phpMyAdmin-${VERSION}-all-languages.tar.gz" | tar --strip-components=1 -x -z
RUN rm -rf *.md .coveralls.yml ChangeLog composer.json config.sample.inc.php DCO doc examples phpunit.* README RELEASE-DATE-* setup
ADD config /config

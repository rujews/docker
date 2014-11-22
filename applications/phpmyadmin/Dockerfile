FROM rujews/nginx-php:latest
MAINTAINER Max Schaefer <max@excloo.com>
ENV VERSION 4.2.12
RUN mkdir -p /data/nginx/www/phpmyadmin
RUN wget -O - "http://www.sourceforge.net/projects/phpmyadmin/files/phpMyAdmin/${VERSION}/phpMyAdmin-${VERSION}-all-languages.tar.gz/download" | tar --strip-components=1 -x -z
RUN rm -rf *.md .coveralls.yml ChangeLog composer.json config.sample.inc.php DCO doc examples phpunit.* README RELEASE-DATE-* setup
ADD config /config
ADD data /data

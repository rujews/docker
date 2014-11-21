FROM rujews/debian:latest
MAINTAINER Max Schaefer <max@excloo.com>
ENV MARIADB_DB NONE
ENV MARIADB_USER docker
RUN apt-get install -y python-software-properties
RUN apt-key adv --recv-keys --keyserver keyserver.ubuntu.com 0xcbcb082a1bb943db
RUN add-apt-repository 'deb http://mirrors.hustunique.com/mariadb/repo/10.0/debian wheezy main'
RUN apt-get update
RUN apt-get install -y mariadb-server
RUN sed -i -e "s/^bind-address/#bind-address/" /etc/mysql/my.cnf
RUN sed -i -e "s/^datadir.*=.*/datadir = \/data/lib/mysql" /etc/mysql/my.cnf
RUN sed -i -e "s/^innodb_buffer_pool_size.*=.*/innodb_buffer_pool_size = 64M/" /etc/mysql/my.cnf
ADD config /config
ADD supervisord.conf /etc/supervisor/conf.d/mariadb.conf
EXPOSE 3306

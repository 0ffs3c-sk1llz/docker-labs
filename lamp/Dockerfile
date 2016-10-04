FROM debian_custom:latest
MAINTAINER 0ffs3c-sk1llz <0ffs3c-sk1llz@hmamail.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
    apache2\
    php5\
    mysql-server\
    php5-mysql

CMD service rsyslog start && service ssh start && service apache2 restart && service mysql start && tail -f /var/log/syslog

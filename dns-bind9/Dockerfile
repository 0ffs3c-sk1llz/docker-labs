FROM debian_custom:latest

RUN apt-get update && apt-get -y dist-upgrade
RUN apt-get -y install bind9 

#ADD db.0ffs3c-sk1llz /etc/bind/db.0ffs3c-sk1llz
#ADD db.10 /etc/bind/db.10
#ADD named.conf.local /etc/bind/named.conf.local

CMD service rsyslog start && service bind9 start && service ssh start && tail -f /var/log/syslog

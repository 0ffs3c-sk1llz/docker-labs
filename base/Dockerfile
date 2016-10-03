FROM debian:latest

RUN adduser --gecos GECOS --disabled-password ctf
RUN echo 'ctf:ctf' | chpasswd

RUN apt-get update && apt-get -y dist-upgrade
RUN apt-get -y install rsyslog openssh-server vim dnsutils sudo net-tools

RUN adduser ctf sudo

CMD service rsyslog start && service ssh start && tail -f /var/log/syslog

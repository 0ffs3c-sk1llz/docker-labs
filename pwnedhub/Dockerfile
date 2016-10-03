FROM debian_custom:latest
MAINTAINER 0ffs3c-sk1llz <0ffs3c-sk1llz@hmamail.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
    python-pip python-dev libxml2-dev libxslt1-dev libmysqlclient-dev

COPY files /home/ctf/files
RUN cd /home/ctf/files \
	&& pip install -r REQUIREMENTS.txt \
	&& python -c 'import pwnedhub; pwnedhub.initdb()'
	

CMD service rsyslog start && service ssh start && cd /home/ctf/files && python ./pwnedhub.py && tail -f /var/log/syslog

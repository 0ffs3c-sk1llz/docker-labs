FROM debian_custom:latest
MAINTAINER 0ffs3c-sk1llz <0ffs3c-sk1llz@hmamail.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
    python-pip python-dev uwsgi-plugin-python \
    nginx supervisor

COPY flask.conf /etc/nginx/sites-available/
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY app /var/www/app

RUN mkdir -p /var/log/nginx/app /var/log/uwsgi/app /var/log/supervisor \
    && rm /etc/nginx/sites-enabled/default \
    && ln -s /etc/nginx/sites-available/flask.conf /etc/nginx/sites-enabled/flask.conf \
    && echo "daemon off;" >> /etc/nginx/nginx.conf \
    &&  pip install -r /var/www/app/requirements.txt \
    && chown -R www-data:www-data /var/www/app \
    && chown -R www-data:www-data /var/log

CMD service rsyslog start && service ssh start && /usr/bin/supervisord && tail -f /var/log/syslog

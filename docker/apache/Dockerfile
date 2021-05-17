FROM httpd:2.4.43-alpine

RUN apk update; \
    apk upgrade;

RUN echo "Include /srv/docker/apache/apache.conf"  >> /usr/local/apache2/conf/httpd.conf

FROM nginx:latest

MAINTAINER ojh102@naver.com
VOLUME ["/var/www/html", "/var/log/nginx", "/data/run","/etc/nginx/conf.d"]

RUN sed "s|user  nginx;|user www-data;|" /etc/nginx/nginx.conf > /etc/nginx/nginx.conf.bak1 \
    && sed "s|worker_processes  1;|worker_processes  4;|" /etc/nginx/nginx.conf.bak1 > /etc/nginx/nginx.conf.bak2 \
    && mv /etc/nginx/nginx.conf.bak2 /etc/nginx/nginx.conf

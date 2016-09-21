FROM debian:latest

MAINTAINER ojh102@naver.com

### package for php start ###

RUN apt-get update && apt-get install -y --no-install-recommends \
		ca-certificates \
		curl \
		wget \
		git \
	&& rm -rf /var/lib/apt/lists/*
RUN apt-get update \
    && apt-get install -y --no-install-recommends curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*
RUN echo "deb http://packages.dotdeb.org jessie all" > /etc/apt/sources.list.d/dotdeb.list \
    && curl -sS https://www.dotdeb.org/dotdeb.gpg | apt-key add - \
    && apt-get update \
    && apt-get install -y --no-install-recommends php7.0-fpm php7.0-readline \
    && apt-get -y --no-install-recommends install php7.0-fpm  php7.0-bcmath php7.0-bz2 php7.0-curl \
    php7.0-dba php7.0-dev php7.0-enchant php7.0-geoip php7.0-gmp php7.0-igbinary php7.0-imagick \
    php7.0-intl php7.0-redis  php7.0-snmp \
    php7.0-soap php7.0-ssh2 php7.0-tidy php7.0-xdebug php7.0-xmlrpc php7.0-apcu php7.0-apcu-bc php7.0-curl \
    php7.0-json php7.0-mcrypt php7.0-opcache php7.0-readline php7.0-xml php7.0-zip \
    php7.0-redis php7.0-mongo php7.0-mongodb \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*
RUN apt-get update 
RUN apt-get install -y --no-install-recommends tesseract-ocr*
RUN curl -s https://packagecloud.io/install/repositories/phalcon/stable/script.deb.sh | bash
RUN apt-get install -y --no-install-recommends php7.0-phalcon


VOLUME [/var/www/html]
VOLUME [/run/php]

RUN echo '[global]' > /etc/php/7.0/fpm/pool.d/docker.conf
RUN echo 'daemonize = no' >> /etc/php/7.0/fpm/pool.d/docker.conf
#RUN apt-get install -y php7.0-redis
#RUN apt-get install -y php7.0-mongodb

#EXPOSE 80

#ENTRYPOINT service nginx start && service php7.0-fpm start && bash
CMD ["php-fpm7.0"]

RUN apt-get update && apt-get install php7.0-mysql
RUN apt-get install php7.0-mbstring

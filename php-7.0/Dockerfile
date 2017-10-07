FROM debian:jessie
MAINTAINER Christophe Vuagniaux <cvx@cvxnet.ch>

ADD composer-install.sh /tmp/composer-install.sh

RUN \
    DEBIAN_FRONTEND=noninteractive \
    apt-get update && \
    apt-get install -y wget && \

    echo "deb http://packages.dotdeb.org jessie all" >> /etc/apt/sources.list && \
    wget -O- https://www.dotdeb.org/dotdeb.gpg | apt-key add - && \

    DEBIAN_FRONTEND=noninteractive \
    apt-get update && \
    apt-get install -y \
        php7.0-cli \
        php7.0-mysql php7.0-curl php7.0-gd php7.0-imap php7.0-mcrypt php7.0-imagick \
        php7.0-json php7.0-intl php7.0-gmp php7.0-geoip php7.0-mbstring php7.0-xml php7.0-zip \
        tmux vim zip unzip curl && \

    rm -fr /var/lib/apt/lists/* && \

    wget https://phar.phpunit.de/phpunit.phar && \
    chmod +x phpunit.phar && \
    mv phpunit.phar /usr/local/bin/phpunit && \

    chmod +x /tmp/composer-install.sh && \
    sync && \
    /tmp/composer-install.sh && \
    rm /tmp/composer-install.sh && \

    chsh -s /bin/bash www-data # allow to use www-data (su www-data) with uid 33

CMD ["bash"]
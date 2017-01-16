FROM php:7.0
MAINTAINER devon <admin@fanxiao2.net>

WORKDIR /usr/share/nginx/html

# 常用工具
RUN apt-get update && apt-get install -y git curl wget cron vim locales libfreetype6-dev mariadb-client \
  && rm -rf /var/lib/apt/lists/* \
  && pecl install zip \
  && docker-php-ext-enable zip \
  && docker-php-ext-install mysqli pdo_mysql

RUN echo "PS1='[console]# '" >> /root/.bashrc

# 配置 git
RUN git config --global user.name "DevonChina" \
  && git config --global user.email "admin@fanxiao2.net"

# 安装与配置 composer
# Composer 安装是否成功取决于网络，这里我是用的国内Composer全量站提供的安装方式，如果不成功，建议大家可以把文件下载到本地然后进行COPY安装
# RUN php -r "readfile('https://getcomposer.org/installer');" > composer-setup.php
# RUN php composer-setup.php
# RUN php -r "unlink('composer-setup.php');" \
# RUN mv composer.phar /usr/local/bin/composer
# RUN chmod +x /usr/local/bin/composer
# RUN echo 'export PATH="$PATH:$HOME/.composer/vendor/bin"' >> ~/.bashrc \
#   && . ~/.bashrc \
#   && composer config -g repo.packagist composer https://packagist.phpcomposer.com

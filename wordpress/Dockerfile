FROM php:7.2-apache

# composerをインストール
RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer \
    && chmod +x /usr/local/bin/composer

# パッケージのリストをサーバーから入手
RUN apt-get update

# PHPからMySQLに繋ぐための準備
RUN docker-php-ext-install pdo_mysql

# PHPのExtensionをインストール．
RUN docker-php-ext-install mysqli mbstring

# zip,unzip,git,vimをインストール
RUN apt-get install -y zip unzip git vim

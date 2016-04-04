FROM dpb587/ci-calt:ubuntu-trusty
RUN true \
  && apt-get update && apt-get install -y libmcrypt-dev libreadline-dev re2c libxml2-dev bison pkg-config libssl-dev libcurl4-gnutls-dev libpng-dev libjpeg-dev libtidy-dev libxslt1-dev \
  && apt-get purge -y && apt-get autoremove -y && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
  && git clone git://github.com/php-build/php-build.git && cd php-build && ./install.sh && cd - && rm -fr php-build \
  && php-build -i development 5.4.45 /opt/php \
  && echo 'date.timezone = UTC' >> /opt/php/etc/conf.d/defaults.ini \
  && wget -O /opt/php/bin/composer https://getcomposer.org/composer.phar && chmod +x /opt/php/bin/composer \
  && wget -O /opt/php/bin/phpunit https://phar.phpunit.de/phpunit-old.phar && chmod +x /opt/php/bin/phpunit
ADD calt /opt/calt
ENV PATH="/opt/php/bin:/opt/php/sbin:$PATH"

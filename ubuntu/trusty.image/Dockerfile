FROM ubuntu:14.04
RUN true \
  && locale-gen en_US.UTF-8 && dpkg-reconfigure locales \
  && apt-get update && apt-get install -y autoconf build-essential git curl wget \
  && apt-get purge -y && apt-get autoremove -y && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
  && groupadd -g 555 calt && useradd -u 555 -g 555 -m calt && echo 'calt ALL=NOPASSWD:ALL' >> /etc/sudoers
ADD calt /opt/calt
ENV LANG=en_US.UTF-8
ENV LC_ALL=en_US.UTF-8
ENV PATH="/opt/calt/sbin:$PATH"
ENTRYPOINT /opt/calt/sbin/calt-run

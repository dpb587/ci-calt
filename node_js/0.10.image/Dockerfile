FROM dpb587/ci-calt:ubuntu-trusty
RUN true \
  && mkdir /opt/node \
  && curl -o- https://nodejs.org/download/release/v0.10.44/node-v0.10.44-linux-x64.tar.xz | tar -xJf- -C /opt/node --strip-components 1
ADD calt /opt/calt
ENV PATH="/opt/node/bin:$PATH"

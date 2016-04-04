FROM dpb587/ci-calt:ubuntu-trusty
RUN true \
  && eval "$(curl -sL https://raw.githubusercontent.com/travis-ci/gimme/master/gimme | GIMME_GO_VERSION=1.6 bash)" \
  && mv /root/.gimme/versions/go1.6.linux.amd64 /opt/go
ADD calt /opt/calt
ENV PATH="/opt/go/bin:$PATH"

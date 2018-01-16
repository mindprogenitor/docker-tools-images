FROM alpine:edge

WORKDIR /root
COPY install_input /tmp/install_input

RUN apk --no-cache add \
  bash \
  curl \
  jq \
  tar \
  openssl \
  python \
  gcc \
  libffi \
  libffi-dev \
  libc-dev \ 
  python-dev \
  openssl-dev \
  make ; \
  curl -L https://aka.ms/InstallAzureCli | sed s/XXXX/XXXXXX/ | sed s/_TTY=\\/dev\\/tty// | sed s/'< $_TTY'// > /tmp/install_azure_cli.sh ; \
  bash /tmp/install_azure_cli.sh < /tmp/install_input ; \
  apk del \
  openssl-dev \
  libffi-dev \
  python-dev \
  libc-dev \
  gcc \
  make \
  tar \
  apk-tools ; \
  rm -fr /tmp/* ; \
  rm -fr /var/cache/apk

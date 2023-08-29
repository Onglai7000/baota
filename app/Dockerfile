ARG UBUNTU_VERSION
FROM ubuntu:${UBUNTU_VERSION}
LABEL maintainer="ifui <ifui@foxmail.com>"

RUN groupadd -f www && useradd -g www www

ARG BAOTA_INSTALL_PATH
# install pkg
RUN apt-get install -y wget \
    && apt-get install -y ca-certificates \
    && apt-get install -y gd

# install baota
RUN set -eux \
    && wget -O install.sh ${BAOTA_INSTALL_PATH} \
    && echo y | sh install.sh

COPY app.sh /

RUN chmod 777 /app.sh

CMD [ "/app.sh" ]

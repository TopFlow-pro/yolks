# ----------------------------------
# Environment: redis
# ----------------------------------
FROM    --platform=$TARGETOS/$TARGETARCH eqalpha/keydb:alpine

LABEL   author="Michael Parker" maintainer="parker@pterodactyl.io"

ENV     DEBIAN_FRONTEND noninteractive

RUN apk update && apk add bash
RUN apk add iproute2

RUN adduser -D -h /home/container container

USER    container
ENV     USER=container HOME=/home/container
WORKDIR /home/container

COPY    ./entrypoint.sh /entrypoint.sh
CMD     ["/bin/bash", "/entrypoint.sh"]
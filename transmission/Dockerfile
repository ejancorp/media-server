FROM alpine:latest

RUN apk update && \
    apk upgrade && \
    apk add transmission-daemon && \
    rm -rf /var/cache/apk/*

ADD transmission/settings.json /etc/transmission-daemon/settings.json

VOLUME /volumes/media
VOLUME /etc/transmission-daemon

EXPOSE 9091
EXPOSE 51413
EXPOSE 51413/udp

CMD ["/usr/bin/transmission-daemon", "-f", "-g", "/etc/transmission-daemon"]
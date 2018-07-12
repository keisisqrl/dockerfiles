FROM alpine:3.6

RUN apk add --no-cache curl s6 ca-certificates \
    && curl -L 'https://caddyserver.com/download/linux/amd64?plugins=net&license=personal&telemetry=on' \
    | tar xzf - caddy \
    && chmod +x caddy \
    && mv caddy /usr/bin \
    && apk del curl


ENV CADDYPATH /caddy-data
ENV CA_URI https://acme-staging-v02.api.letsencrypt.org/directory

VOLUME /caddy-data

ADD Caddyfile /

CMD ["caddy","-conf=/Caddyfile","-type=net","-agree"]

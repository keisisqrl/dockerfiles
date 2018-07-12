FROM alpine:3.6

ENV CADDYPATH /caddy-data
ENV CA_URI https://acme-staging.api.letsencrypt.org/directory

RUN apk add --no-cache curl s6 ca-certificates 
    && curl -L 'https://caddyserver.com/download/linux/amd64?plugins=net&license=personal&telemetry=on' \
    | tar xzf - caddy \
    && chmod +x caddy \
    && mv caddy /usr/bin \
    && apk del curl

VOLUME /caddy-data

CMD ["caddy","-conf=/caddy-data/Caddyfile","-type=net"]

FROM alpine

RUN apk add --no-cache icecast

EXPOSE 8080/tcp

CMD icecast -c /etc/icecast.xml
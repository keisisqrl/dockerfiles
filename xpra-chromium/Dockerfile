FROM alpine

RUN apk add --no-cache xpra chromium

EXPOSE 10000

CMD xpra start --start-child=chromium --bind-tcp=0.0.0.0:10000 --exit-with-children --daemon=no

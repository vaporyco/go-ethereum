FROM alpine:3.7

RUN \
  apk add --update go git make gcc musl-dev linux-headers ca-certificates && \
  git clone --depth 1 https://github.com/vaporyco/go-vapory && \
  (cd go-vapory && make gvap) && \
  cp go-vapory/build/bin/gvap /gvap && \
  apk del go git make gcc musl-dev linux-headers && \
  rm -rf /go-vapory && rm -rf /var/cache/apk/*

EXPOSE 8575
EXPOSE 10801

ENTRYPOINT ["/gvap"]

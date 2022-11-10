FROM alpine:3.16 AS build

RUN apk update && apk add tar wget gcc make musl-dev ncurses-dev && \
    mkdir /work && \
    wget http://x3270.bgp.nu/download/04.02/suite3270-4.2ga6-src.tgz -O x3270.tgz && \
    tar -zxf x3270.tgz -C /work && \
    cd /work/suite3270-4.2 && \
    ./configure --enable-c3270 && \
    make && make install DESTDIR=/work/result


# minimal environment for running
FROM alpine:3.16

RUN apk update && apk add ncurses && rm -rf /var/cache/apk/*
COPY --from=build /work/result /

ENTRYPOINT ["sh"]

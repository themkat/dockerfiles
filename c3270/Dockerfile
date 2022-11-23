FROM alpine:3.16 AS build

RUN apk add --no-cache tar wget gcc make musl-dev ncurses-dev && \
    mkdir /work && \
    wget -q http://x3270.bgp.nu/download/04.02/suite3270-4.2ga6-src.tgz -O x3270.tgz && \
    tar -zxf x3270.tgz -C /work && \
    cd /work/suite3270-4.2 && \
    ./configure --enable-c3270 && \
    make && make install DESTDIR=/work/result


# minimal environment for running
FROM alpine:3.16

RUN apk add --no-cache ncurses
COPY --from=build /work/result /

ENTRYPOINT ["sh"]

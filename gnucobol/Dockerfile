FROM alpine:3.8

# TODO: find a shorter url
RUN apk add make gcc musl-dev gmp-dev db-dev ncurses-dev && \
	rm -rf /var/cache/apk/* && \
	wget -O gnucobol.tar.gz "https://downloads.sourceforge.net/project/open-cobol/gnu-cobol/3.0/gnucobol-3.0-rc1.tar.gz?r=https%3A%2F%2Fsourceforge.net%2Fprojects%2Fopen-cobol%2Ffiles%2Fgnu-cobol%2F3.0%2Fgnucobol-3.0-rc1.tar.gz%2Fdownload&ts=1542134743" && \
	tar -zxvf gnucobol.tar.gz && \
	rm gnucobol.tar.gz && \
	cd gnucobol* && \
	./configure && \
	make install && \
	cd .. && \
	rm -rf gnucobol*


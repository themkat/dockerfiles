FROM alpine:3.10 as build

RUN apk add ncurses-dev git make libc-dev gcc --no-cache && \
	git clone https://github.com/visit1985/mdp.git && \
	cd mdp && \
	make && \
	make install 


FROM alpine:3.10

RUN apk add ncurses --no-cache

# Keeps only the binary as man is not installed
COPY --from=build /usr/local/bin/mdp /usr/local/bin/mdp

ENTRYPOINT ["/bin/sh"]

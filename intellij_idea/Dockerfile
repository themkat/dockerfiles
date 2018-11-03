FROM openjdk:8-alpine

RUN apk add ttf-dejavu && \
	rm -rf /var/cache/apk/* && \
	wget -O idea.tar.gz https://download.jetbrains.com/idea/ideaIC-2018.2.5.tar.gz && \
	tar -zxvf idea.tar.gz && \
	mv idea-* idea && \
	rm idea.tar.gz

ENTRYPOINT ["./idea/bin/idea.sh"]

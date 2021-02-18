# prefer alpine to create small images, but got a lot of problems because of musl :(
# (java executables expect glibc)
FROM debian:buster-slim

# java needs man folder to exist, because reasons :P 
RUN mkdir -p /usr/share/man/man1 && \
	apt-get update && \
	apt-get install -y ttf-dejavu wget libxext6 libxtst6 libxrender1 libfreetype6 openjdk-11-jdk && \
	apt-get clean && \
	wget -q -O idea.tar.gz https://download.jetbrains.com/idea/ideaIC-2020.3.2.tar.gz && \
	tar -zxf idea.tar.gz && \
	mv idea-* idea && \
	rm idea.tar.gz

ENTRYPOINT ["./idea/bin/idea.sh"]

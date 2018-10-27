# is there a better base image? I only picked a small recently new debian
FROM debian:buster-slim
LABEL maintainer "Marie K. Ekeberg (mke@themkat.net)"

# TODO: add xfvb to have a "virtual framebuffer" to avoid gtk errors
# TODO: remove apt cache and do other stuff to make image smaller.
RUN apt-get update && \
	apt-get install -y openjdk-8-jdk emacs build-essential wget --no-install-recommends && \
	wget -O eclipse.tar.gz https://mirrors.dotsrc.org/eclipse//technology/epp/downloads/release/2018-09/R/eclipse-java-2018-09-linux-gtk-x86_64.tar.gz && \
	tar -zxvf eclipse.tar.gz / && \
	rm eclipse.tar.gz && \
	wget -O eclim.bin https://github.com/ervandew/eclim/releases/download/2.8.0/eclim_2.8.0.bin && \
	./eclim.bin --yes --eclipse=/eclipse && \
	rm eclim.bin

ENTRYPOINT ["/opt/eclipse/eclimd"]

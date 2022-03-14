FROM quay.io/buildah/stable:v1.23.1

RUN yum install -y python3-pip podman && \
	pip3 install ansible ansible-bender

WORKDIR "/home/build"
ENTRYPOINT "/bin/bash"

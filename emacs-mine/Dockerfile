# Just a setup ready to use with my own Emacs setup :P for science...
# useful to doublecheck that my setup work for other OS (like gnu/linux) than my goto Macbook Air M1
FROM debian:bullseye-slim

RUN apt-get update && apt-get install -y git emacs && \
    useradd devguy && mkdir -p /home/devguy && \
    git clone https://github.com/themkat/.emacs.d.git /home/devguy/.emacs.d && \
    chown -R devguy /home/devguy && \
    apt-get clean

USER devguy
ENTRYPOINT "bash"

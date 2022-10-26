FROM --platform=linux/386 debian/eol:squeeze

WORKDIR /work/dslinux
RUN apt-get update && \
    apt-get install -y subversion wget bzip2 gcc binutils make \
    libncurses-dev zlib1g-dev gettext libperl-dev texinfo \
    flex bison gawk less file && \
    apt-get clean && \
    useradd devguy && \
    wget http://dslinux.org/toolchain/dslinux-toolchain-2008-01-24-i686.tbz && \
    tar -C /usr/local -jxf dslinux-toolchain-2008-01-24-i686.tbz && \
    rm dslinux-toolchain-2008-01-24-i686.tbz && \
    cd /work && svn checkout http://svn.dslinux.org/svn/trunk dslinux && \
    cd dslinux && svn update && chown -R devguy .

ENV PATH=/usr/local/dslinux-toolchain-2008-01-24-i686/bin:$PATH
USER devguy
ENTRYPOINT ["bash"]

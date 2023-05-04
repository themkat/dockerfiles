FROM amigadev/crosstools:m68k-amigaos

# include some libraries that is useful (and that I often use)
# - curl
# - amissl
# - zlib

RUN wget http://aminet.net/util/libs/AmiSSL-5.8-SDK.lha && \
    lha x AmiSSL-5.8-SDK.lha && \
    cp -R AmiSSL/Developer/include /opt/m68k-amigaos/. && \
    cp AmiSSL/Developer/lib/AmigaOS3/libamisslauto.a /opt/m68k-amigaos/lib/. && \
    rm AmiSSL-5.8-SDK.lha && \
    wget http://aminet.net/comm/tcp/curl-7.74.0.lha && \
    lha x curl-7.74.0.lha && \
    cp -R curl-7.74.0/opt/amiga/* /opt/m68k-amigaos/. && \
    rm curl-7.74.0.lha && \
    wget http://aminet.net/dev/lib/zlib_68k.lha && \
    lha x zlib_68k.lha && \
    cp -R zlib_68k/nofpu/include /opt/m68k-amigaos/. && \
    cp zlib_68k/nofpu/lib/libz.a /opt/m68k-amigaos/lib/. && \
    rm zlib_68k.lha

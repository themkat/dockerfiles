FROM amigadev/crosstools:ppc-amigaos

# TODO: other stuff we should include?
RUN wget -O mui.lha https://github.com/amiga-mui/muidev/releases/download/MUI-5.0-20210831/MUI-5.0-20210831-os4.lha && \
    lha x mui.lha && \
    cp -R SDK/MUI/C/include/* /opt/ppc-amigaos/ppc-amigaos/include/. && \
    rm -rf SDK MUI mui.lha

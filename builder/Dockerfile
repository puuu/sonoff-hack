FROM debian:10

USER root

WORKDIR opt


RUN apt-get update && \
    apt-get install -y git unzip build-essential libtool bison bisonc++ libbison-dev autoconf autotools-dev automake libssl-dev zlib1g-dev libzzip-dev flex libfl-dev yui-compressor closure-compiler optipng jpegoptim libtidy5deb1 node-less sassc sass-spec libhtml-tidy-perl libxml2-utils rsync wget bzip2 && \
    apt-get clean

# for toolchain
RUN dpkg --add-architecture i386 && apt-get update && \
    apt-get install -y libstdc++6:i386 libgcc1:i386 zlib1g:i386 && \
    apt-get clean

RUN wget -q https://github.com/roleoroleo/sonoff-hack/releases/download/toolchain-0.0.1/arm-sonoff-linux-uclibcgnueabi.tgz && \
    tar xf arm-sonoff-linux-uclibcgnueabi.tgz && rm -rf arm-sonoff-linux-uclibcgnueabi.tgz 

ENV PATH=${PATH}:/opt/arm-sonoff-linux-uclibcgnueabi/bin/

# for toolchain gdb
RUN apt-get install -y libncurses5:i386 libpython2.7:i386 && \
    apt-get clean
RUN ln -s libpython2.7.so.1.0 /usr/lib/i386-linux-gnu/libpython2.6.so.1.0

VOLUME /build
WORKDIR /build

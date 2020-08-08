FROM gcc:7.4.0
ENV PATH $PATH:/usr/local/sh-tools/bin
ENV LD_LIBRARY_PATH /usr/local/gmp/lib:/usr/local/mpfr/lib:/usr/local/mpc/lib:$LD_LIBRARY_PATH
RUN apt-get update && apt-get install -y --no-install-recommends texinfo && rm -rf /var/lib/apt/lists/*
RUN mkdir /build \
&& cd /build \
&& wget -nv https://ftp.gnu.org/gnu/binutils/binutils-2.30.tar.xz \
&& tar Jxf binutils-2.30.tar.xz \
&& mkdir -p binutils-2.30/build \
&& cd binutils-2.30/build \
&& ../configure -q --target=sh-elf --prefix=/usr/local/sh-tools \
&& make -s -j8 \
&& make -s install \
&& cd / \
&& rm -rf build
RUN mkdir /build \
&& cd /build \
&& wget -nv https://gmplib.org/download/gmp/gmp-6.1.2.tar.xz \
&& tar Jxf gmp-6.1.2.tar.xz \
&& mkdir -p gmp-6.1.2/build \
&& cd gmp-6.1.2/build \
&& ../configure -q --prefix=/usr/local/gmp \
&& make -s -j8 \
&& make -s install \
&& cd / \
&& rm -rf build
RUN mkdir /build \
&& cd /build \
&& wget -nv https://ftp.gnu.org/gnu/mpfr/mpfr-4.0.2.tar.xz \
&& tar Jxf mpfr-4.0.2.tar.xz \
&& mkdir -p mpfr-4.0.2/build \
&& cd mpfr-4.0.2/build \
&& ../configure -q --with-gmp=/usr/local/gmp --prefix=/usr/local/mpfr \
&& make -s -j8 \
&& make -s install \
&& cd / \
&& rm -rf build
RUN mkdir /build \
&& cd /build \
&& wget -nv https://ftp.gnu.org/gnu/mpc/mpc-1.1.0.tar.gz \
&& tar zxf mpc-1.1.0.tar.gz \
&& mkdir -p mpc-1.1.0/build \
&& cd mpc-1.1.0/build \
&& ../configure -q --with-gmp=/usr/local/gmp --with-mpfr=/usr/local/mpfr --prefix=/usr/local/mpc \
&& make -s -j8 \
&& make -s install \
&& cd / \
&& rm -rf build
RUN mkdir /build \
&& cd /build \
&& wget -nv http://ftp.tsukuba.wide.ad.jp/software/gcc/releases/gcc-7.4.0/gcc-7.4.0.tar.xz \
&& tar Jxf gcc-7.4.0.tar.xz \
&& mkdir -p gcc-7.4.0/build \
&& cd gcc-7.4.0/build \
&& ../configure -q --target=sh-elf --prefix=/usr/local/sh-tools --with-gmp=/usr/local/gmp --with-mpfr=/usr/local/mpfr --with-mpc=/usr/local/mpc --enable-languages=c --disable-libssp \
&& make -s -j8 \
&& make -s install \
&& cd / \
&& rm -rf build
RUN mkdir /build \
&& cd /build \
&& wget -nv ftp://sourceware.org/pub/newlib/newlib-3.0.0.tar.gz \
&& tar zxf newlib-3.0.0.tar.gz \
&& mkdir -p newlib-3.0.0/build \
&& cd newlib-3.0.0/build \
&& ../configure -q --target=sh-elf --prefix=/usr/local/sh-tools \
&& make -s -j8 \
&& make -s install \
&& cd / \
&& rm -rf build
RUN mkdir /build \
&& cd /build \
&& wget -nv ftp://sourceware.org/pub/newlib/newlib-3.0.0.tar.gz \
&& tar zxf newlib-3.0.0.tar.gz \
&& wget -nv http://ftp.tsukuba.wide.ad.jp/software/gcc/releases/gcc-7.4.0/gcc-7.4.0.tar.xz \
&& tar Jxf gcc-7.4.0.tar.xz \
&& mkdir -p gcc-7.4.0/build \
&& cd gcc-7.4.0/build \
&& ../configure -q --target=sh-elf --prefix=/usr/local/sh-tools --with-gmp=/usr/local/gmp --with-mpfr=/usr/local/mpfr --with-mpc=/usr/local/mpc --enable-languages=c --disable-libssp -with-newlib -with-headers=/build/newlib-3.0.0/newlib/libc/include \
&& make -s -j8 \
&& make -s install \
&& cd / \
&& rm -rf build

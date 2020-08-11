FROM moku828/gcc-sh-elf:7.4.0
RUN mkdir /build \
&& cd /build \
&& wget -nv https://ftp.gnu.org/gnu/gdb/gdb-8.1.tar.xz \
&& tar Jxf gdb-8.1.tar.xz \
&& mkdir -p gdb-8.1/build \
&& cd gdb-8.1/build \
&& ../configure -q --target=sh-elf --prefix=/usr/local/sh-tools \
&& make -s -j8 \
&& make -s install \
&& cd / \
&& rm -rf build

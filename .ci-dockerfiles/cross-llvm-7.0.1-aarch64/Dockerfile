FROM ponylang/ponyc-ci:llvm-7.0.1

ARG CROSS_TRIPLE=aarch64-unknown-linux-gnu
ARG CROSS_CC=aarch64-linux-gnu-gcc
ARG CROSS_CXX=aarch64-linux-gnu-g++
ARG CROSS_CFLAGS=
ARG CROSS_CXXFLAGS=
ARG CROSS_LDFLAGS=
ARG CROSS_BITS=64
ARG CROSS_LINKER=aarch64-linux-gnu-gcc
ARG CROSS_TUNE=cortex-a53

ARG QEMU_VERSION=2.12.0
ARG COMPILER_RELEASE=2018.05

USER root

RUN wget "https://releases.linaro.org/components/toolchain/binaries/6.4-${COMPILER_RELEASE}/aarch64-linux-gnu/gcc-linaro-6.4.1-${COMPILER_RELEASE}-x86_64_aarch64-linux-gnu.tar.xz" \
 && tar xJvf gcc-linaro-6.4.1-${COMPILER_RELEASE}-x86_64_aarch64-linux-gnu.tar.xz -C /usr/local --strip 1 \
 && aarch64-linux-gnu-gcc --version \
 && rm gcc-linaro-6.4.1-${COMPILER_RELEASE}-x86_64_aarch64-linux-gnu.tar.xz \
 && wget https://github.com/multiarch/qemu-user-static/releases/download/v${QEMU_VERSION}/qemu-aarch64-static -O /usr/bin/qemu-aarch64-static \
 && chmod +x /usr/bin/qemu-aarch64-static

USER pony
WORKDIR /home/pony

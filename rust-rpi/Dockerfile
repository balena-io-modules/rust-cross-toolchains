FROM majorz/rust-rpi:rust-1.23.0

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    make && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Setup Rust for ARMv6 cross-compilation

ARG RUST_VERSION

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y

RUN rustup target add arm-unknown-linux-gnueabihf

# Get the ARMv6 libssl-dev package from Raspbian.

ARG CROSS_TRIPLE=arm-linux-gnueabihf

ARG SYSROOT=/root/sysroot

RUN cd $SYSROOT && \
    curl -L --remote-name http://mirrordirector.raspbian.org/raspbian/pool/main/o/openssl/libssl-dev_1.1.0f-3+deb9u1_armhf.deb && \
    ar p libssl-dev_1.1.0f-3+deb9u1_armhf.deb data.tar.xz | tar xJ

ENV OPENSSL_LIB_DIR=$SYSROOT/usr/lib/$CROSS_TRIPLE

ENV OPENSSL_INCLUDE_DIR=$SYSROOT/usr/include

RUN cp $SYSROOT/usr/include/$CROSS_TRIPLE/openssl/* $SYSROOT/usr/include/openssl

VOLUME /work

WORKDIR /work

FROM debian:jessie

ARG CROSS_TRIPLE=i686-linux-gnu

RUN dpkg --add-architecture i386 && \
    apt-get update && \
    apt-get install -y --no-install-recommends \
    ca-certificates \
    curl \
    git \
    gcc \
    libc6-dev \
    pkg-config \
    g++-multilib \
    libdbus-1-dev:i386 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN ln -s /usr/bin/strip /usr/bin/cross-strip


# Setup Rust for x86_32 cross-compilation

ARG RUST_VERSION

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y

ENV PATH=/root/.cargo/bin:$PATH

RUN rustup target add i686-unknown-linux-gnu

ENV PKG_CONFIG_ALLOW_CROSS=1 \
    PKG_CONFIG_LIBDIR=/usr/lib/i386-linux-gnu/pkgconfig/


VOLUME /work

WORKDIR /work

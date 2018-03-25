FROM majorz/rust-armv7hf:rust-1.23.0

ARG CROSS_TRIPLE=arm-linux-gnueabihf

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    make \
    libssl-dev:armhf && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Setup Rust for ARMv7 cross-compilation

ARG RUST_VERSION

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y

RUN rustup target add armv7-unknown-linux-gnueabihf


VOLUME /work

WORKDIR /work

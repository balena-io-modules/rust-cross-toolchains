FROM majorz/rust-aarch64:rust-1.23.0

ARG CROSS_TRIPLE=aarch64-linux-gnu

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    make \
    libssl-dev:arm64 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Setup Rust for AArch64 cross-compilation

ARG RUST_VERSION

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y

RUN rustup target add aarch64-unknown-linux-gnu


VOLUME /work

WORKDIR /work

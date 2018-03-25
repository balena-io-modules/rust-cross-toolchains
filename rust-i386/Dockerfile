FROM majorz/rust-i386:rust-1.23.0

ARG CROSS_TRIPLE=i686-linux-gnu

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    make \
    libssl-dev:i386 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Setup Rust for x86_32 cross-compilation

ARG RUST_VERSION

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y

RUN rustup target add i686-unknown-linux-gnu


VOLUME /work

WORKDIR /work

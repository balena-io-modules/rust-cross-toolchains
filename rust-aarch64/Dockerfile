FROM majorz/rust-aarch64:rust-1.23.0

# Setup Rust for AArch64 cross-compilation

ARG RUST_VERSION

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y

RUN rustup target add aarch64-unknown-linux-gnu


VOLUME /work

WORKDIR /work

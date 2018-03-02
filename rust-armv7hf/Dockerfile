FROM majorz/rust-armv7hf:rust-1.23.0

# Setup Rust for ARMv7 cross-compilation

ARG RUST_VERSION

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y

RUN rustup target add armv7-unknown-linux-gnueabihf


VOLUME /work

WORKDIR /work

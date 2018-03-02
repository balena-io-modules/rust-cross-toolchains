FROM majorz/rust-rpi:rust-1.23.0

# Setup Rust for ARMv6 cross-compilation

ARG RUST_VERSION

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y

RUN rustup target add arm-unknown-linux-gnueabihf


VOLUME /work

WORKDIR /work

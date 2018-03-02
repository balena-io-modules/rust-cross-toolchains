FROM majorz/rust-i386:rust-1.23.0

# Setup Rust for x86_32 cross-compilation

ARG RUST_VERSION

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y

RUN rustup target add i686-unknown-linux-gnu


VOLUME /work

WORKDIR /work

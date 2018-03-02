FROM majorz/rust-amd64:rust-1.23.0

# Setup Rust for x86_64 compilation

ARG RUST_VERSION

ENV PATH=/root/.cargo/bin:$PATH

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y


VOLUME /work

WORKDIR /work

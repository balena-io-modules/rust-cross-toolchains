FROM majorz/rust-amd64:rust-1.23.0

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    make \
    libssl-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Setup Rust for x86_64 compilation

ARG RUST_VERSION

ENV PATH=/root/.cargo/bin:$PATH

RUN rustup self uninstall -y

RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain ${RUST_VERSION} -y


VOLUME /work

WORKDIR /work

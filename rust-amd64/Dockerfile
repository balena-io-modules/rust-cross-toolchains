FROM debian:jessie

RUN apt-get update && \
    apt-get install  -y --no-install-recommends \
    ca-certificates \
    curl \
    git \
    gcc \
    g++ \
    libc6-dev \
    pkg-config \
    libdbus-1-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*


RUN ln -s /usr/bin/strip /usr/bin/cross-strip


RUN curl https://sh.rustup.rs -sSf | sh -s -- -y

ENV PATH=/root/.cargo/bin:$PATH


VOLUME /work

WORKDIR /work

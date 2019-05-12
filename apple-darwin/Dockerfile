FROM multiarch/crossbuild:latest

SHELL ["/bin/bash", "-c"]
ENV CROSS_TRIPLE "x86_64-apple-darwin"

# Set up Darwin linker
COPY ./crossbuild-linker /usr/local/bin/

# Muck with the PATH so we can find dsymutil
ENV PATH=${PATH}:/usr/x86_64-apple-darwin14/bin:/root/.cargo/bin

# Get latest stable Rust set-up and add Darwin target
RUN set -euo pipefail && \
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y; \
    rustup target add x86_64-apple-darwin; \
    :

COPY ./cargo-config.toml /root/.cargo/config

# Example command
# cargo build --release --target x86_64-apple-darwin

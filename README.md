# `rust-crossbuild`

Crossbuild set-up for Rust compilation for OSX and Windows.

## How to use Docker image to build OSX Rust binaries

```bash
docker build apple-darwin/ -t guangie88/rust-crossbuild:x86_64-apple-darwin

docker run --rm -it -v $(pwd):/workdir \
    guangie88/rust-crossbuild:x86_64-apple-darwin \
    cargo build --release --target x86_64-apple-darwin
```

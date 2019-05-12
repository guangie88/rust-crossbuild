# `rust-crossbuild`

Dockerfile set-up to get Rust cross-compilation for OSX and Windows.

This set-up enhances the original
[`crossbuild`](https://github.com/multiarch/crossbuild) such that building
the Rust binary for OSX and Windows is just one Docker command away.

## How to use Docker image to build OSX Rust binaries

```bash
docker build apple-darwin/ -t guangie88/rust-crossbuild:x86_64-apple-darwin

docker run --rm -it -v $(pwd):/workdir \
    guangie88/rust-crossbuild:x86_64-apple-darwin \
    cargo build --release --target x86_64-apple-darwin
```

## How to use Docker image to build Windows MinGW Rust binaries

WIP

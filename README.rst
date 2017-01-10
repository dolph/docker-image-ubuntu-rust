Docker Image: Ubuntu (stable) + Rust (nightly)
==============================================

This repo contains a Concourse CI pipeline to build a docker image based on
Ubuntu (latest stable release). The image contains nothing more than `rustc`
and `cargo` for building Rust-based binaries and libraries.

This image is [published on Docker
Hub](https://hub.docker.com/r/dolphm/ubuntu-latest-rust-nightly/) and updated
daily.

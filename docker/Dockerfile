FROM ubuntu:latest

RUN apt-get update
RUN apt-get install -y apt-utils
RUN apt-get install -y curl gcc
RUN curl https://sh.rustup.rs -sSf > /tmp/rustup-init.sh
RUN chmod +x /tmp/rustup-init.sh
RUN sh /tmp/rustup-init.sh -y
RUN rm -rf /tmp/rustup-init.sh
ENV PATH "$PATH:~/.cargo/bin"

# Update the local crate index
RUN cargo search

# Initialize a dummy project so that we can pre-download the latest versions of
# the most popular crates.
RUN mkdir /tmp/dummy-crate
WORKDIR /tmp/dummy-crate
RUN cargo init

# Choose a selection of useful crates to download (and all their deps).
RUN echo "hyper = '*'" >> Cargo.toml
RUN echo "itertools = '*'" >> Cargo.toml
RUN echo "log = '*'" >> Cargo.toml
RUN echo "matches = '*'" >> Cargo.toml
RUN echo "num = '*'" >> Cargo.toml
RUN echo "rand = '*'" >> Cargo.toml
RUN echo "regex = '*'" >> Cargo.toml
RUN echo "semver = '*'" >> Cargo.toml
RUN echo "tempdir = '*'" >> Cargo.toml
RUN echo "time = '*'" >> Cargo.toml
RUN echo "url = '*'" >> Cargo.toml

# Build the empty project, in order to download the crates.
RUN cargo build

# Clean up the dummy crate
RUN rm -rf /tmp/dummy-crate

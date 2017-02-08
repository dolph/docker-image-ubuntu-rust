FROM ubuntu:latest

RUN apt-get update
RUN apt-get install -y apt-utils
RUN apt-get install -y curl gcc
RUN curl https://sh.rustup.rs -sSf > /tmp/rustup-init.sh
RUN chmod +x /tmp/rustup-init.sh
RUN sh /tmp/rustup-init.sh -y
RUN rm -rf /tmp/rustup-init.sh

ENV PATH "$PATH:~/.cargo/bin"

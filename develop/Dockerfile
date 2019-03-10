FROM moratorium08/riscv-toolchain:rv32gc

RUN apt-get update && apt-get install -y \
        curl \
        python3 \
        python3-dev\
        python3-pip

RUN pip3 install pipenv

ADD rustup-init /rustup-init

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y --no-modify-path --default-toolchain nightly-2019-02-01-x86_64-unknown-linux-gnu

ENV PATH=/root/.cargo/bin:$PATH

RUN rustup component add rust-src && cargo install cargo-xbuild --version=0.5.4

ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8

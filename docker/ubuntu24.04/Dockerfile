FROM ubuntu:noble

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update -y

RUN apt install build-essential python3 python-is-python3 \
                    qt6-base-dev qt6-5compat-dev qt6-translations-l10n \
                    qt6-tools-dev-tools qt6-base-dev-tools qt6-tools-dev \
                    libboost-dev libssl-dev libcurl4-openssl-dev \
                    ragel ninja-build zlib1g-dev git \
                    wget fuse file -y && \
    apt clean && rm -rf /var/lib/apt/lists/*

RUN wget https://github.com/Kitware/CMake/releases/download/v3.20.2/cmake-3.20.2-linux-x86_64.sh && \
    chmod 755 cmake-3.20.2-linux-x86_64.sh && \
    ./cmake-3.20.2-linux-x86_64.sh --prefix=/opt/ --exclude-subdir --skip-license

ENV PATH=/opt/bin:$PATH

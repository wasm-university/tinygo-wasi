FROM gitpod/workspace-full

USER gitpod

RUN sudo apt-get update && \
    sudo apt-get install gettext libncurses5 libxkbcommon0 libtinfo5 -y

# GoLang
#ARG GO_VERSION="1.17.5"
#RUN curl -sL https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer| bash

#RUN ["/bin/bash", "-c", ". /home/gitpod/.gvm/scripts/gvm && gvm install go1.17.5 -B"]
#RUN ["/bin/bash", "-c", ". /home/gitpod/.gvm/scripts/gvm && gvm use go1.17.5"]

# TinyGo
ARG TINYGO_VERSION="0.23.0"
RUN wget https://github.com/tinygo-org/tinygo/releases/download/v${TINYGO_VERSION}/tinygo_${TINYGO_VERSION}_amd64.deb
RUN sudo dpkg -i tinygo_${TINYGO_VERSION}_amd64.deb
RUN rm tinygo_${TINYGO_VERSION}_amd64.deb

# ------------------------------------
# Install tools
# ------------------------------------
RUN brew install httpie && \
    brew install bat && \
    brew install exa && \
    brew install hey

RUN curl -sSf https://raw.githubusercontent.com/WasmEdge/WasmEdge/master/utils/install.sh | bash && \
    curl https://get.wasmer.io -sSfL | sh && \
    curl https://wasmtime.dev/install.sh -sSf | bash

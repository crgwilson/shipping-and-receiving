FROM debian:10
WORKDIR /build/neovim
RUN apt-get update && \
  apt-get install -y build-essential devscripts lintian quilt ninja-build gettext libtool libtool-bin autoconf \
    automake cmake g++ pkg-config unzip curl doxygen gperf libacl1-dev liblua5.1-dev libmsgpack-dev libnss-wrapper \
    libtermkey-dev libunibilium-dev libuv1-dev libvterm-dev locales lua-bitop lua-busted \
    lua-filesystem lua-inspect lua-lpeg lua-luv-dev lua-mpack lua-nvim lua5.1 && \
  git clone https://github.com/neovim/neovim /build/neovim
COPY ./debian /build/neovim/debian
RUN cd /build && tar cvzf neovim_0.6.0-dev-525.orig.tar.gz neovim
RUN cd /build/neovim && debuild

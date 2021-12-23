ARG base_compiler
ARG base_tag

FROM ghcr.io/yuki-cpp/ubuntu_${base_tag}:${base_compiler}

RUN add-apt-repository -y ppa:ubuntu-toolchain-r/test
RUN apt-get update
RUN apt-get install -y g++-11 gcc-11

# Setup default compilers to clang-14 variations
RUN update-alternatives --remove-all c++
RUN update-alternatives --remove-all cc

RUN update-alternatives --install /usr/bin/c++ c++ /usr/bin/g++-11 10
RUN update-alternatives --install /usr/bin/cc cc /usr/bin/gcc-11 10

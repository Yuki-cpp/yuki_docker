ARG base_tag

FROM ghcr.io/yuki-cpp/ubuntu_${base_tag}:default

RUN mkdir llvm_setup
RUN cd llvm_setup
RUN bash -c "$(wget -O - https://apt.llvm.org/llvm.sh)"
RUN wget https://apt.llvm.org/llvm.sh
RUN chmod +x llvm.sh
RUN ./llvm.sh 15
RUN cd ..
RUN rm -rf llvm_setup

#Install all required packages
RUN apt-get update
RUN apt-get -y install libllvm-15-ocaml-dev libllvm15 llvm-15 llvm-15-dev llvm-15-doc llvm-15-runtime
RUN apt-get -y install clang-15 clang-tools-15 clang-15-doc libclang-common-15-dev libclang-15-dev libclang1-15 clang-format-15 clangd-15
RUN apt-get -y install libc++-15-dev libc++abi-15-dev
RUN apt-get -y install lldb-15
RUN apt-get -y install libfuzzer-15-dev
RUN apt-get -y install libomp-15-dev
RUN apt-get -y install libclc-15-dev
RUN apt-get -y install libunwind-15-dev

# Setup default compilers to clang-15 variations
RUN update-alternatives --remove-all c++
RUN update-alternatives --remove-all cc

RUN update-alternatives --install /usr/bin/c++ c++ /usr/bin/clang++-15 10
RUN update-alternatives --install /usr/bin/cc cc /usr/bin/clang-15 10

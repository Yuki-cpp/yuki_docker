ARG base_tag

FROM ghcr.io/yuki-cpp/ubuntu_${base_tag}:default

RUN mkdir llvm_setup
RUN cd llvm_setup
RUN bash -c "$(wget -O - https://apt.llvm.org/llvm.sh)"
RUN wget https://apt.llvm.org/llvm.sh
RUN chmod +x llvm.sh
RUN ./llvm.sh 12
RUN cd ..
RUN rm -rf llvm_setup

#Install all required packages
RUN apt-get update
RUN apt-get -y install libllvm-12-ocaml-dev libllvm12 llvm-12 llvm-12-dev llvm-12-doc llvm-12-runtime
RUN apt-get -y install clang-12 clang-tools-12 clang-12-doc libclang-common-12-dev libclang-12-dev libclang1-12 clang-format-12 clangd-12
RUN apt-get -y install libc++-12-dev libc++abi-12-dev
RUN apt-get -y install lldb-12
RUN apt-get -y install libfuzzer-12-dev
RUN apt-get -y install libomp-12-dev
RUN apt-get -y install libclc-12-dev
RUN apt-get -y install libunwind-12-dev

# Setup default compilers to clang-12 variations
RUN update-alternatives --remove-all c++
RUN update-alternatives --remove-all cc

RUN update-alternatives --install /usr/bin/c++ c++ /usr/bin/clang++-12 10
RUN update-alternatives --install /usr/bin/cc cc /usr/bin/clang-12 10

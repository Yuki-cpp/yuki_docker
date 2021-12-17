FROM ubuntu:20.04

#Install tooling
RUN apt-get update
RUN apt-get -y install apt-transport-https ca-certificates gnupg software-properties-common wget

# Get external repos
RUN wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null | apt-key add -
RUN apt-add-repository 'deb https://apt.kitware.com/ubuntu/ focal main'

RUN mkdir llvm_setup
RUN cd llvm_setup
RUN bash -c "$(wget -O - https://apt.llvm.org/llvm.sh)"
RUN wget https://apt.llvm.org/llvm.sh
RUN chmod +x llvm.sh
RUN ./llvm.sh 13
RUN cd ..
RUN rm -rf llvm_setup

#Install all required packages
RUN apt-get update
RUN apt-get -y install git
RUN apt-get -y install libllvm-13-ocaml-dev libllvm13 llvm-13 llvm-13-dev llvm-13-doc llvm-13-examples llvm-13-runtime
RUN apt-get -y install clang-13 clang-tools-13 clang-13-doc libclang-common-13-dev libclang-13-dev libclang1-13 clang-format-13 clangd-13
RUN apt-get -y install libc++-13-dev libc++abi-13-dev
RUN apt-get -y install lldb-13
RUN apt-get -y install libfuzzer-13-dev
RUN apt-get -y install libomp-13-dev
RUN apt-get -y install libclc-13-dev
RUN apt-get -y install libunwind-13-dev
RUN apt-get -y install cmake
RUN apt-get -y install python3-pip

# Setup default compilers to clang-13 variations
RUN update-alternatives --remove-all c++
RUN update-alternatives --remove-all cc

RUN update-alternatives --install /usr/bin/c++ c++ /usr/bin/clang++-13 10
RUN update-alternatives --install /usr/bin/cc cc /usr/bin/clang-13 10

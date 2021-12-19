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
RUN ./llvm.sh 14
RUN cd ..
RUN rm -rf llvm_setup

#Install all required packages
RUN apt-get update
RUN apt-get -y install git
RUN apt-get -y install libllvm-14-ocaml-dev libllvm14 llvm-14 llvm-14-dev llvm-14-doc llvm-14-examples llvm-14-runtime
RUN apt-get -y install clang-14 clang-tools-14 clang-14-doc libclang-common-14-dev libclang-14-dev libclang1-14 clang-format-14 clangd-14
RUN apt-get -y install libc++-14-dev libc++abi-14-dev
RUN apt-get -y install lldb-14
RUN apt-get -y install libfuzzer-14-dev
RUN apt-get -y install libomp-14-dev
RUN apt-get -y install libclc-14-dev
RUN apt-get -y install libunwind-14-dev
RUN apt-get -y install cmake
RUN apt-get -y install python3-pip

#Install conan
RUN pip install conan

# Setup default compilers to clang-14 variations
RUN update-alternatives --remove-all c++
RUN update-alternatives --remove-all cc

RUN update-alternatives --install /usr/bin/c++ c++ /usr/bin/clang++-14 10
RUN update-alternatives --install /usr/bin/cc cc /usr/bin/clang-14 10

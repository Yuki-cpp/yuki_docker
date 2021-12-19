FROM ubuntu:20.04

#Install tooling
RUN apt-get update
RUN apt-get -y install apt-transport-https ca-certificates gnupg software-properties-common wget

# Get external repos
RUN wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null | apt-key add -
RUN apt-add-repository 'deb https://apt.kitware.com/ubuntu/ focal main'

#Install all required packages
RUN apt-get update
RUN apt-get -y install git
RUN apt-get -y install cmake
RUN apt-get -y install python3-pip

#Install conan
RUN pip install conan

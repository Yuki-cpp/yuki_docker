ARG version

FROM ubuntu:${version}

#Install tooling
RUN apt-get update
RUN apt-get -y install apt-transport-https ca-certificates gnupg software-properties-common wget unzip apt-utils curl

# Get external repos
RUN wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null | apt-key add -
RUN apt-add-repository "deb https://apt.kitware.com/ubuntu/ $(lsb_release -cs) main"

#Install all required packages
RUN apt-get update
RUN apt-get -y install git cmake python3-pip openjdk-11-jdk

#Install conan
RUN pip3 install conan

#Install vcpkg
RUN mkdir /vcpkg
RUN git clone https://github.com/Microsoft/vcpkg.git /vcpkg
RUN /vcpkg/bootstrap-vcpkg.sh
ENV VCPKG_TOOLCHAIN "/vcpkg/scripts/buildsystems/vcpkg.cmake"

#Install sonar
RUN mkdir /sonar
RUN wget -O /sonar/sonar-scanner.zip https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.6.1.2450-linux.zip
RUN unzip -o /sonar/sonar-scanner.zip -d /sonar

#Install sonar build wrapper
RUN wget -O /sonar/build-wrapper-linux-x86.zip https://sonarcloud.io/static/cpp/build-wrapper-linux-x86.zip
RUN unzip -o /sonar/build-wrapper-linux-x86.zip -d /sonar
RUN cp /sonar/build-wrapper-linux-x86/build-wrapper-linux-x86-64 /sonar/build-wrapper-linux-x86/sonar-build-wrapper

#Setup paths
ENV PATH "PATH=$PATH:/sonar/sonar-scanner-4.6.1.2450-linux/bin"
ENV PATH "PATH=$PATH:/sonar/build-wrapper-linux-x86"

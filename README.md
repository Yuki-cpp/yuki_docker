# yuki_docker
This repository provides a number of Docker images with pre-installed software.

## Available images
Images for the following OS are currently provided:
- Ubuntu 18.04
- Ubuntu 20.04

## Images contents
Each image comes pre-installed with the following software:
- `git` (latest version available on the OS default package manager)
- `python` (latest version available on the OS `pip3` package manager)
- `cmake` (latest version available on the OS Kitware package repository)

For each image, the following tags are available:
- `default` : The default flavor of the OS, with no addition software (except the ones mentioned above) installed.
- `clang-12` : A version of the OS where the default C and C++ compilers (`cc` and `c++`) are set to use the clang-12 versions (`clang-12` and `clang++-12`). 
In addition `clang-tidy-12` and `clang-format-12` are also provided.
- `clang-13` : A version of the OS where the default C and C++ compilers (`cc` and `c++`) are set to use the clang-13 versions (`clang-13` and `clang++-13`). 
In addition `clang-tidy-13` and `clang-format-13` are also provided.
- `gcc-10` : A version of the OS where the default C and C++ compilers (`cc` and `c++`) are set to use the gcc-10 versions (`gcc-10` and `g++-10`). 
In addition `clang-tidy-13` and `clang-format-13` are also provided.
- `gcc-11` : A version of the OS where the default C and C++ compilers (`cc` and `c++`) are set to use the gcc-11 versions (`gcc-11` and `g++-11`). 
In addition `clang-tidy-13` and `clang-format-13` are also provided.


----
## Docker Images Release Status
<table>
    <thead>
        <tr>
            <th>OS</th>
            <th>Status</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=1>
              <a href="https://github.com/Yuki-cpp/yuki_docker/pkgs/container/ubuntu_18_04">Ubuntu 18.04</a>
            </td>
            <td rowspan=2>
              <a href="https://github.com/Yuki-cpp/yuki_docker/actions/workflows/release_ubuntu_images.yml">
                <img src="https://github.com/Yuki-cpp/yuki_docker/actions/workflows/release_ubuntu_images.yml/badge.svg?branch=master" alt="Build passing">
              </a>
            </td>
        </tr>
        <tr>
          <td rowspan=1>
            <a href="https://github.com/Yuki-cpp/yuki_docker/pkgs/container/ubuntu_20_04">Ubuntu 20.04</a>
          </td>
        </tr>
    </tbody>
</table>

----

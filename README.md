# yuki_docker
This repository provides a number of Docker images with pre-installed software.

## Available images
Images for the following OS are currently provided:
- Ubuntu 18.04
- Ubuntu 20.04

## Images contents
Each image comes pre-installed with the following software:
- `git` (latest version available on the OS default package manager)
- `conan` (latest version available on the OS `pip3` package manager)
- `cmake` (latest version available on the OS Kitware package repository)
- `sonar-scanner` and the sonar build wrapper (version `4.6.1.2450`. Both are added to the path and a `sonar-build-wrapper` alias exists for the wrapper.

For each image, the following tags are available:
- `default` : The default flavor of the OS, with no addition software (except the ones mentioned above) installed.
- `clang-12` : A version of the OS where the default C and C++ compilers (`cc` and `c++`) are set to use the clang-12 versions (`clang-12` and `clang++-12`). 
In addition `clang-tidy-12` and `clang-format-12` are also provided.
- `clang-13` : A version of the OS where the default C and C++ compilers (`cc` and `c++`) are set to use the clang-13 versions (`clang-13` and `clang++-13`). 
In addition `clang-tidy-13` and `clang-format-13` are also provided.
- `clang-14` : A version of the OS where the default C and C++ compilers (`cc` and `c++`) are set to use the clang-14 versions (`clang-14` and `clang++-14`). 
In addition `clang-tidy-14` and `clang-format-14` are also provided. This compiler is only available with Ubuntu 20.04.
- `gcc-10` : A version of the OS where the default C and C++ compilers (`cc` and `c++`) are set to use the gcc-10 versions (`gcc-10` and `g++-10`). 
In addition `clang-tidy-13` and `clang-format-13` are also provided.
- `gcc-11` : A version of the OS where the default C and C++ compilers (`cc` and `c++`) are set to use the gcc-11 versions (`gcc-11` and `g++-11`). 
In addition `clang-tidy-13` and `clang-format-13` are also provided.


----
## Docker Images Release Status
<table>
    <colgroup>
       <col span="1" style="width: 25%;">
       <col span="1" style="width: 25%;">
       <col span="1" style="width: 25%;">
       <col span="1" style="width: 25%;">
    </colgroup>
    <thead>
        <tr>
            <th>OS</th>
            <th>default</th>
            <th>clang</th>
            <th>gcc</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          Ubuntu 18.04
        </td>
        <td>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/18.04_default/18.04_default.svg">
        </td>
        <td>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/18.04_clang-12/18.04_clang-12.svg"><br>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/18.04_clang-13/18.04_clang-13.svg">
        </td>
        <td>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/18.04_gcc-10/18.04_gcc-10.svg"><br>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/18.04_gcc-11/18.04_gcc-11.svg">
        </td>
      </tr>
      <tr>
        <td>
          Ubuntu 20.04
        </td>
        <td>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/20.04_default/20.04_default.svg">
        </td>
        <td>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/20.04_clang-12/20.04_clang-12.svg"><br>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/20.04_clang-13/20.04_clang-13.svg"><br>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/20.04_clang-14/20.04_clang-14.svg">
        </td>
        <td>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/20.04_gcc-10/20.04_gcc-10.svg"><br>
          <img src="https://raw.githubusercontent.com/Yuki-cpp/yuki_docker/tags/tags/20.04_gcc-11/20.04_gcc-11.svg">
        </td>
      </tr>
    </tbody>
</table>

----

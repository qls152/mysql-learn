# mysql构建文档

本文主要针对mysql中cmake中内容的学习记录

# 文档讲解

> MESSAGE(STATUS "Running cmake version ${CMAKE_VERSION}")

MESSAGE用法可参考：[message](https://cmake.org/cmake/help/v3.24/command/message.html?highlight=message)

简单来说，就是在构建mysql时，cmake会首先输出上述语句

> IF(WIN32)

IF用法可参考：[IF](https://cmake.org/cmake/help/v3.24/command/if.html?highlight=#command:if)

WIN32为CMAKE的自定义变量，当在Windows平台时其为True，否则为False

> FIND_PROGRAM(MY_CMAKE3 cmake3 /bin /usr/bin /usr/local/bin)

find_program：参考[find_program](https://cmake.org/cmake/help/v3.24/command/find_program.html?highlight=find_program)

find_program在/bin /usr/bin /usr/local/bin路径中搜索cmake3，若搜到结果，则程序名保存在MY_CMAKE3变量中

> CMAKE_MINIMUM_REQUIRED(VERSION 3.5.1)

其用法可参考[CMAKE_MINIMUM_REQUIRED](https://cmake.org/cmake/help/v3.24/command/cmake_minimum_required.html?highlight=cmake_minimum_required)

设置构建mysql项目所需要的最小的cmake版本号

> FIND_PACKAGE(Git)

[FIND_PACKAGE](https://cmake.org/cmake/help/v3.24/command/find_package.html?highlight=find_package)


>  参考
>
> [CMake Tutorial — CMake 3.31.0-rc2 Documentation](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)

# 1、Step 1: A Basic Staring Point

## 1.1、Building a Basic Project

最基本的 `CMake Project` 是一个可执行的源文件，其 `CMakeLists.txt` 配置文件只有三个配置参数。

> 注意：虽然CMake支持大小写混合的命令，但建议使用小写命令，本教程将始终使用小写命令。

任何 `CMakeLists.txt` 文件都需要由 `cmake_miniumum_required()` 开头，指定 `CMake` 的最小版本。

使用 `project()` 命令创建一个项目，并设定项目的名称，一般都是在 `cmake_miniumum_required()` 之后调用。`project()` 用于指定编程语言，版本号这些项目参数。

最后使用 `add_executable()` 命令告诉 `CMake` 用那些源代码创建可执行文件。

```cmake
cmake_minimum_required(VERSION 3.10)
project(Tutorial)
add_executable(Tutorial tutorial.cxx)
```



## 1.2、Specifying the C++ Standard

`CMake`有一些特殊的变量，这些变量要么是在幕后创建的，要么是在项目代码中设置的。这些变量中有许多以`CMAKE_`开头。





```cmake
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)
```







## 1.3、Adding a Version Number and Configured Header File
















# OpenCV-with-Contrib-MinGW-Build

> 推荐Windows用户使用`MSYS2`安装`OpenCV with Contrib`，此Repo停止更新

MinGW 64bit version of OpenCV with opencv_contrib compiled on Windows.

## Install

### Step 1: Clone this repo

```sh
git clone --depth=1 https://github.com/SunYufei/OpenCV-with-Contrib-MinGW-Build OpenCV
```

### Step 2: Add the following folder(s) to your system PATH

```
OpenCV/
OpenCV/x64/mingw/bin
```

### Step 3: Add OpenCV packages to your CMakeLists.txt

```cmake
cmake_minimum_required(VERSION 3.0)

project(ProjectName)

set(CMAKE_CXX_STANDARD 11)
set(OpenCV_DIRS /path/to/OpenCV)

find_package(OpenCV REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})

link_libraries(${OpenCV_LIBS})
```

## Thanks

[OpenCV-MinGW-Build](https://github.com/huihut/OpenCV-MinGW-Build)

# OpenCV-with-Contrib-MinGW-Build

MinGW 64bit version of OpenCV with opencv_contrib compiled on Windows.

## Install

### Step 1: Clone this repo

```sh
git clone --depth=1 https://github.com/SunYufei/OpenCV-with-Contrib-MinGW-Build OpenCV
```

### Step 2: Add the following folder(s) to your system PATH

```
OpenCV/
```

### Step 3: Add OpenCV packages to your CMakeLists.txt

```cmake
cmake_minimum_required(VERSION 3.0)

project(ProjectName)

set(CMAKE_CXX_COMPILER g++)

find_package(OpenCV REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(${PROJECT_NAME} "main.cpp")

target_link_libraries(${PROJECT_NAME} ${OpenCV_LIBS})
```

## Thanks

[OpenCV-MinGW-Build](https://github.com/huihut/OpenCV-MinGW-Build)
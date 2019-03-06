# OpenCV-with-Contrib-MinGW-Build

> 此Repo为OpenCV with Contrib 4.0.1 MinGW编译版本，不再更新

## 推荐

推荐使用`MSYS2`安装`OpenCV`和`OpenCV Contrib`模块

```sh
pacman -S mingw-w64-x86_64-toolchain
pacman -S mingw-w64-x86_64-opencv
```

将下列目录添加到系统环境变量`path`中

```
/path/to/MSYS2/mingw64/bin
```

### Makefile Template

```makefile
CC = g++

CFLAGS += -g -Wall -I/path/to/MSYS2/mingw64/include/opencv4

LDFLAGS += -L/path/to/MSYS2/mingw64/lib \
	-lopencv_aruco \
	-lopencv_bgsegm \
	-lopencv_calib3d \
	-lopencv_ccalib \
	-lopencv_core \
	-lopencv_datasets \
	-lopencv_dnn -lopencv_dnn_objdetect \
	-lopencv_dpm \
	-lopencv_face \
	-lopencv_features2d -lopencv_xfeatures2d \
	-lopencv_flann \
	-lopencv_fuzzy \
	-lopencv_gapi \
	-lopencv_hdf \
	-lopencv_hfs \
	-lopencv_highgui \
	-lopencv_img_hash \
	-lopencv_imgcodecs -lopencv_imgproc -lopencv_ximgproc \
	-lopencv_line_descriptor \
	-lopencv_ml \
	-lopencv_objdetect -lopencv_xobjdetect \
	-lopencv_optflow \
	-lopencv_ovis \
	-lopencv_phase_unwrapping \
	-lopencv_photo -lopencv_xphoto \
	-lopencv_plot \
	-lopencv_reg \
	-lopencv_rgbd \
	-lopencv_saliency \
	-lopencv_sfm \
	-lopencv_shape \
	-lopencv_stereo \
	-lopencv_stitching \
	-lopencv_structured_light \
	-lopencv_superres \
	-lopencv_surface_matching \
	-lopencv_text \
	-lopencv_tracking \
	-lopencv_video -lopencv_videoio -lopencv_videostab \
	-lopengl32 \
	-lglu32

TARGET = # target
OBJS += # obj files

all:$(TARGET)
$(TARGET):$(OBJS)
	$(CC) $(CFLAGS) $(OBJS) -o $(TARGET) $(LDFLAGS)
$(OBJS):%.o:%.cpp
	$(CC) $(CFLAGS) -c $< -o $@


.PHONY:clean
clean:
	rm -r $(OBJS) $(TARGET)
```

## 以下是原内容

MinGW 64bit version of OpenCV with opencv_contrib compiled on Windows.

### Install

#### Step 1: Clone this repo

```sh
git clone --depth=1 https://github.com/SunYufei/OpenCV-with-Contrib-MinGW-Build OpenCV
```

#### Step 2: Add the following folder(s) to your system PATH

```
OpenCV/
OpenCV/x64/mingw/bin
```

#### Step 3: Add OpenCV packages to your CMakeLists.txt

```cmake
cmake_minimum_required(VERSION 3.0)

project(ProjectName)

set(CMAKE_CXX_STANDARD 11)
set(OpenCV_DIRS /path/to/OpenCV)

find_package(OpenCV REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})

link_libraries(${OpenCV_LIBS})
```

### Thanks

[OpenCV-MinGW-Build](https://github.com/huihut/OpenCV-MinGW-Build)

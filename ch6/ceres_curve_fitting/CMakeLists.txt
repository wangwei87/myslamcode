cmake_minimum_required(VERSION 2.8)
project(ceres_curve_fitting)

set(CMAKE_BUILD_TYPE "Release")
set(CMAKE_CXX_FLAGS "-std=c++11 -O3")

# 添加cmake模块以使用ceres库
list( APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake_modules)

find_package(Ceres REQUIRED)
include_directories(${CERES_INCLUDE_DIRS})

find_package(OpenCV REQUIRED)
include_directories(${OpenCV_DIRS})

add_executable(ceres_curve_fitting main.cpp)

target_link_libraries(ceres_curve_fitting ${CERES_LIBRARIES} ${OpenCV_LIBS} )

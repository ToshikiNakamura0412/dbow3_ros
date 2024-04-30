cmake_minimum_required(VERSION 3.0.2)
project(dbow3_ros)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  roscpp
)
find_package(OpenCV REQUIRED)

###################################
## catkin specific configuration ##
###################################
catkin_package(
  INCLUDE_DIRS DBow3/src
  LIBRARIES dbow3_ros
)

###########
## Build ##
###########
include_directories(
  DBow3/src
  ${catkin_INCLUDE_DIRS}
  ${OpenCV_INCLUDE_DIRS}
)

## Declare a C++ library
FILE(GLOB hdrs "DBow3/src/*.h")
FILE(GLOB srcs1 "DBow3/src/*.c")
FILE(GLOB srcs2 "DBow3/src/*.cpp")
add_library(${PROJECT_NAME}
  ${hdrs}
  ${srcs1}
  ${srcs2}
)
add_dependencies(${PROJECT_NAME}
  ${${PROJECT_NAME}_EXPORTED_TARGETS}
  ${catkin_EXPORTED_TARGETS}
  ${OpenCV_LIBS}
)

## Declare a C++ executable
add_executable(demo_general
  DBow3/utils/demo_general.cpp
)
add_dependencies(demo_general
  ${${PROJECT_NAME}_EXPORTED_TARGETS}
  ${catkin_EXPORTED_TARGETS}
)
target_link_libraries(demo_general
  ${catkin_LIBRARIES}
  ${OpenCV_LIBS}
  ${PROJECT_NAME}
)

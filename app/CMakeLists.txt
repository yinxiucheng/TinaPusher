cmake_minimum_required(VERSION 3.4.1)

#引入指定目录下的 CMakeLists.text
add_subdirectory(src/main/cpp/librtmp)

#include_directories(src/main/cpp/include)
include_directories(src/main/cpp/include)

add_library(
             native-lib

             SHARED

             src/main/cpp/native-lib.cpp )

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -L${CMAKE_SOURCE_DIR}/src/main/cpp/libs/${ANDROID_ABI}")

target_link_libraries(native-lib
                      rtmp
                      x264
                       log )


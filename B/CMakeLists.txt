cmake_minimum_required(VERSION 3.6.0)

project(B)

add_library(B STATIC B.h B.cpp)

target_include_directories(B PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/mylibB>
  $<INSTALL_INTERFACE:include/mylibB>  # <prefix>/include/mylib
)

target_link_libraries(B PUBLIC A)

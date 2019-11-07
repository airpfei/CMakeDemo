cmake_minimum_required(VERSION 3.6.0)

project(C)

add_library(C SHARED C.h C.cpp)

target_link_libraries(C PRIVATE B)

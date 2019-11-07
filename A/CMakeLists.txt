cmake_minimum_required(VERSION 3.6.0)

project(A)

add_library(A STATIC A.h A.cpp)

install(TARGETS A
    EXPORT XXX
    INCLUDES DESTINATION inc
    PUBLIC_HEADER DESTINATION inc
    LIBRARY DESTINATION lib
)

install(EXPORT XXX DESTINATION pub)

target_include_directories(A
  PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/mylib>
    $<INSTALL_INTERFACE:include/mylibXXX>  # <prefix>/include/mylib 
  PRIVATE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/mylibPV>
)
# INSTALL_INTERFACE export 会生成
# set_target_properties(A PROPERTIES
#   INTERFACE_INCLUDE_DIRECTORIES "${_IMPORT_PREFIX}/include/mylibXXX;${_IMPORT_PREFIX}/inc"
# )


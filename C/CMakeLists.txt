cmake_minimum_required(VERSION 3.6.0)

project(C)

add_library(C SHARED C.h C.cpp)

target_link_libraries(C PRIVATE B)

get_target_property(OUT C LINK_LIBRARIES)
message(STATUS ${OUT})

# CMAKE_XCODE_USE_LINKING_PHASE

# Debug symbols set in XCode project
# set_xcode_property(example GCC_GENERATE_DEBUGGING_SYMBOLS YES "All")

# # Installation
# set(CMAKE_INSTALL_PREFIX "${example-ios_SOURCE_DIR}/../example-app/example-lib")
# install (TARGETS example DESTINATION lib)
# install (FILES ${HEADERS} DESTINATION include)
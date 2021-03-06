##########################################################################################
# ┌──────────────────────────────────────────────────────────────────────────────────────┐
# │                                                                                      │
# │      CMake build script                                                              │
# │  * * * * * * * * * * * * *                                                           │
# │                                                                                      │
# └──────────────────────────────────────────────────────────────────────────────────────┘
##########################################################################################
##########################################################################################
cmake_minimum_required(VERSION 3.13.2 FATAL_ERROR)



##########################################################################################
# ┌──────────────────────────────────────────────────────────────────────────────────────┐
# │  CMake list my source files                                                          │
# └──────────────────────────────────────────────────────────────────────────────────────┘
##########################################################################################

set(HEADER_DIR "${CMAKE_SOURCE_DIR}/include")
set(HEADER_FILES
    "${HEADER_DIR}/foo.hpp"
)

set(SOURCE_FILES
    "foo.cpp"
)



##########################################################################################
# ┌──────────────────────────────────────────────────────────────────────────────────────┐
# │  CMake create my library as static                                                   │
# └──────────────────────────────────────────────────────────────────────────────────────┘
##########################################################################################
add_library("${PROJECT_NAME}" SHARED "${SOURCE_FILES}" "${HEADER_FILES}")    



##########################################################################################
# ┌──────────────────────────────────────────────────────────────────────────────────────┐
# │  CMake library include external libraries                                            │
# └──────────────────────────────────────────────────────────────────────────────────────┘
##########################################################################################
target_link_libraries("${PROJECT_NAME}" PUBLIC "cexception")



##########################################################################################
# ┌──────────────────────────────────────────────────────────────────────────────────────┐
# │  CMake include header directory                                                      │
# └──────────────────────────────────────────────────────────────────────────────────────┘
##########################################################################################
target_include_directories("${PROJECT_NAME}" PUBLIC "${HEADER_DIR}")
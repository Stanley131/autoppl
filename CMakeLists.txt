cmake_minimum_required(VERSION 3.10)
project(AutoPPL LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17) # set C++ standard to C++17

set(AUTOPPL_SOURCE_DIR ${CMAKE_CURRENT_LIST_DIR}/src)
set(AUTOPPL_INCLUDE_DIR ${CMAKE_CURRENT_LIST_DIR}/include/AutoPPL)

set(AUTOPPL_SOURCE_FILES ${AUTOPPL_SOURCE_DIR}/main.cpp)
set(AUTOPPL_HEADER_FILES ${AUTOPPL_INCLUDE_DIR}/autoppl.h)

add_executable(autoppl ${AUTOPPL_SOURCE_FILES} ${AUTOPPL_HEADER_FILES})
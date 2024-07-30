cmake_minimum_required(VERSION 3.15)
project(ARCH)

set(CMAKE_CXX_STANDARD 17)

include_directories(matrix_optimizations/src)

add_library(arch_lib
        matrix_optimizations/include/matrix.h
        matrix_optimizations/src/matrix.cpp)

add_executable(driver matrix_optimizations/tests/driver.cpp
        matrix_optimizations/include/matrix.h
        matrix_optimizations/src/matrix.cpp)
target_link_libraries(driver arch_lib)

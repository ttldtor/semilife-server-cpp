cmake_minimum_required(VERSION 3.20)
project(slscpp)

set(CMAKE_CXX_STANDARD 20)

option(slscpp_use_conan "Use Conan to build the project" ON)

if (slscpp_use_conan)
    include(${CMAKE_BINARY_DIR}/conan_paths.cmake)
endif (slscpp_use_conan)

find_package(Boost)
find_package(fmt)
add_executable(slscpp src/main.cpp)

target_link_libraries(slscpp PRIVATE Boost::boost fmt::fmt-header-only)
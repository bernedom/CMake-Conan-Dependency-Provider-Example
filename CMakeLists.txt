# Chapter 5 - Example illustrating how to use conan with a conanfile.txt
#
# SPDX-License-Identifier: MIT

cmake_minimum_required(VERSION 3.23)

project(
    hello_world
    VERSION 1.0
    DESCRIPTION
        "C++ project to demonstrate using a conan dependency providers from within CMake"
    LANGUAGES CXX
)

# find the just downloaded package
find_package(fmt 10.2.1 REQUIRED)

# Create a target to build an executable
add_executable(hello src/main.cpp)

# link the fmt library to the executable
target_link_libraries(
    hello
    PRIVATE fmt::fmt
)
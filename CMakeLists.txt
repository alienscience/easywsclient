cmake_minimum_required (VERSION 2.8.11)
project (EASYWSCLIENT)

# Require C++11
add_definitions(-std=c++11)

add_library(easywsclient easywsclient.cpp easywsclient.hpp)

add_executable(example-client-cpp11 example-client-cpp11.cpp easywsclient.hpp)
target_link_libraries(example-client-cpp11 easywsclient)


cmake_minimum_required (VERSION 2.8.11)
project (EASYWSCLIENT)

set(CMAKE_BUILD_TYPE "Debug")

# Require C++11
add_definitions(-std=c++11 -Wall -Weffc++)

# Websocket library
add_library(easywsclient easywsclient.cpp easywsclient.hpp)

# Example
add_executable(example-client-cpp11 example-client-cpp11.cpp easywsclient.hpp)
target_link_libraries(example-client-cpp11 easywsclient)

# Tests
include_directories(SYSTEM test)
include_directories(${CMAKE_SOURCE_DIR})
add_executable(tests test/easywsclient.t.cpp)
target_link_libraries(tests easywsclient)


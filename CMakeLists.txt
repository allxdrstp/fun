cmake_minimum_required(VERSION 3.10)
project(funExample)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(GTEST_DIR "${CMAKE_CURRENT_SOURCE_DIR}")
find_package(GTest REQUIRED)

add_library(fun SHARED func.cpp)

add_executable(funExampleTests test1.cpp)
target_link_libraries(funExampleTests fun ${GTEST_LIBRARIES} ${GTEST_MAIN_LIBRARIES})

enable_testing()
add_test(NAME funExampleTests COMMAND funExampleTests)

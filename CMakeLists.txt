cmake_minimum_required(VERSION 3.15)
project(allndb)

set(CMAKE_CXX_STANDARD 17)

add_executable(allndb src/main.cpp)

enable_testing()

add_executable(tests test/tests.cpp)

find_package(GTest REQUIRED)
target_link_libraries(tests PRIVATE GTest::gtest_main)

include(GoogleTest)
gtest_discover_tests(tests)
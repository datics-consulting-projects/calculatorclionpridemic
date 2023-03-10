cmake_minimum_required(VERSION 3.24)

include(FetchContent)

FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        release-1.11.0
)
FetchContent_MakeAvailable(googletest)

add_library(GTest::GTest INTERFACE IMPORTED)
target_link_libraries(GTest::GTest INTERFACE gtest_main)

add_executable(calculator_test test.cpp)

target_link_libraries(calculator_test
 PRIVATE
  GTest::GTest
 calculator)

add_test(calculator_gtests calculator_test)
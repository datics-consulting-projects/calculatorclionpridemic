cmake_minimum_required(VERSION 3.24)

project(calculatorclionpridemic)

set(CMAKE_CXX_STANDARD 17)
add_executable(calculatorclionpridemic main.cpp)
add_subdirectory(calculator)
add_subdirectory(test)
target_link_libraries(calculatorclionpridemic calculator) 
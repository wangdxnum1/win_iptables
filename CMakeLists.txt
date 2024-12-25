cmake_minimum_required(VERSION 3.20)

project(win_iptables)

set(CMAKE_CXX_STANDARD 17)

add_executable(${PROJECT_NAME} src/main.cc)

add_subdirectory(test)

find_package(GTest REQUIRED)

target_link_libraries(${PROJECT_NAME} gtest::gtest)
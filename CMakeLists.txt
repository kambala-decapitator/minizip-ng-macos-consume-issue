cmake_minimum_required(VERSION 3.18)
project(test LANGUAGES C)
find_package(minizip-ng REQUIRED)

add_library(myLib lib.c)
target_link_libraries(myLib PUBLIC MINIZIP::minizip-ng)

add_executable(test main.c)
target_link_libraries(test PRIVATE myLib)

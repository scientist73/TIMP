cmake_minimum_required(VERSION 3.4)

project(hello_world_app)

set(CMAKE_CXX_STANDART 17)
set(CMAKE_CXX_STANDART_REQUIRED ON)

include_directories("../formatter_lib")
include_directories("../formatter_ex_lib")
add_library(formatter_lib STATIC "../formatter_lib/formatter.cpp")
add_library(formatter_ex_lib STATIC "../formatter_ex_lib/formatter_ex.cpp")

add_executable(hello_world_app hello_world.cpp)
target_link_libraries(hello_world_app formatter_ex_lib formatter_lib)

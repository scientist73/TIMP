cmake_minimum_required(VERSION 3.4)
project(lab03)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories("formatter_lib")
include_directories("formatter_ex_lib")
include_directories("solver_lib")

add_library(formatter_lib STATIC "formatter_lib/formatter.cpp")
add_library(formatter_ex_lib STATIC "formatter_ex_lib/formatter_ex.cpp")
add_library(solver_lib STATIC "solver_lib/solver.cpp")

add_executable(solver "solver_application/equation.cpp")
add_executable(hello "hello_world_application/hello_world.cpp")
target_link_libraries(hello formatter_ex_lib formatter_lib)
target_link_libraries(solver solver_lib formatter_ex_lib formatter_lib)

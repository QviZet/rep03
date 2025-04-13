cmake_minimum_required(VERSION 3.4)
project(formatter)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(formatter STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib/formatter.cpp)
add_library(formatter_ex STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib/formatter_ex.cpp)
add_library(solver STATIC ${CMAKE_CURRENT_SOURCE_DIR}/solver_lib/solver.cpp)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/solver_lib)

add_executable(equation ${CMAKE_CURRENT_SOURCE_DIR}/solver_application/equation.cpp)
add_executable(hello_world ${CMAKE_CURRENT_SOURCE_DIR}/hello_world_application/hello_world.cpp)

target_link_libraries(equation solver formatter_ex formatter)
target_link_libraries(hello_world formatter_ex formatter)



cmake_minimum_required(VERSION 3.6)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project(Simple)
find_package(MPI REQUIRED)
find_package(Injection REQUIRED)

add_library(psip SHARED ${CMAKE_CURRENT_LIST_DIR}/psip.cpp)
link_vnv_file(psip PSIP cpp)

install(TARGETS psip DESTINATION lib)


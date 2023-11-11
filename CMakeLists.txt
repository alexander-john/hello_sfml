cmake_minimum_required(VERSION 3.26)
project(hello_sfml)

set(CMAKE_CXX_STANDARD 17)

add_executable(hello_sfml main.cpp)

set(SFML_STATIC_LIBRARIES TRUE)
set(SFML_DIR C:/SFML-2.6.1/lib/cmake/SFML)
find_package(SFML COMPONENTS system window graphics audio network REQUIRED)

include_directories(C:/SFML-2.6.1/include/SFML)
target_link_libraries(hello_sfml sfml-system sfml-window sfml-graphics sfml-audio)
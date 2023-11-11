# hello_sfml
The purpose of this project is to document as well as share, how to setup SFML using CLion on Windows.

# How to setup
## Download
From the SFML website, https://www.sfml-dev.org/download/sfml/2.6.1/ download WinLibs MSVCRT 13.1.0 (32-bit) which is located in the small red box in the Windows section. Then download GCC 13.1.0 MinGW (DW2) - 32-bit. Once downloaded extract folder and copy it to your root C:/ folder.
## CLion
Once added to the root C:/ folder, open CLion. If you dont have CLion you can download it from https://www.jetbrains.com/clion/. Go through the setup and create a C++ executable. I suggest making a "Projects" folder in the root C:/ folder 
so your project folders and libraries are easily accessible. Once your project is loaded up in CLion, double click the CMakeLists.txt to add the following configurations.
## CMake
You do not need to know CMake to understand how to edit the configurations but if you are a beginner like me it is worth it to go to https://cmake.org/cmake/help/latest/guide/tutorial/index.html just to learn a bit about it. With the CMakeLists.txt
open copy and paste the following:
```cmake
cmake_minimum_required(VERSION 3.26)
project(hello_sfml)

set(CMAKE_CXX_STANDARD 17)

add_executable(hello_sfml main.cpp)

set(SFML_STATIC_LIBRARIES TRUE)
set(SFML_DIR C:/SFML-2.6.1/lib/cmake/SFML)
find_package(SFML COMPONENTS system window graphics audio network REQUIRED)

include_directories(C:/SFML-2.6.1/include/SFML)
target_link_libraries(hello_sfml sfml-system sfml-window sfml-graphics sfml-audio)
```
Note: as you can see when reading the CMake file there are instances of "hello_sfml". Change those instances to the name of your project. Also, change the directories to the appropriate locations that you have on your system. Once complete you should be ready to
build and run!

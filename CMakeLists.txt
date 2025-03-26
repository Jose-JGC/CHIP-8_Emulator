cmake_minimum_required(VERSION 3.10)

# Set the project name
project(CHIP-8_emulator)

# Set C++17 standard
set(CMAKE_CXX_STANDARD 17)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

# Find OpenGL
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

add_executable(CHIP-8_emulator src/main.cpp src/glad.c)

target_include_directories(CHIP-8_emulator PRIVATE include)

target_link_libraries(CHIP-8_emulator ${GLFW3_LIBRARY} OpenGL::GL)
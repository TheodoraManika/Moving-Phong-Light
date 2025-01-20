cmake_minimum_required(VERSION 3.0)
project(phong VERSION 1.0)
cmake_policy(SET CMP0072 NEW)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_SOURCE_DIR}/cmake)
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

add_executable(phong 
    src/config.h
    src/main.cpp
    src/glad.c
)
target_include_directories(phong PRIVATE dependencies)
target_link_libraries(phong glfw3.dll)
target_link_libraries(phong ${GLFW3_LIBRARY} OpenGL::GL)
cmake_minimum_required (VERSION 2.8.11)
project (gl_test)

find_package(GLEW REQUIRED)
find_package(glfw3 CONFIG REQUIRED)

add_executable(gltest test.c)
add_executable(hellotriangle hellotriangle.c)

target_include_directories(gltest PUBLIC $GLEW_INCLUDE_DIR)
target_include_directories(hellotriangle PUBLIC $GLEW_INCLUDE_DIR)

target_link_libraries (gltest PRIVATE GLEW::GLEW glfw GL)
target_link_libraries (hellotriangle PRIVATE GLEW::GLEW glfw GL)

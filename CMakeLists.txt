cmake_minimum_required(VERSION 3.9)

project(GLFWDemo)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "")
set(GLFW_BUILD_TESTS OFF CACHE BOOL "")
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "")
set(GLFW_INSTALL OFF CACHE BOOL "")

add_subdirectory(GLFW)

add_executable(GLFWDemo MACOSX_BUNDLE main.cpp)
target_link_libraries(GLFWDemo glfw)

find_package(OpenGL REQUIRED)
target_include_directories(GLFWDemo SYSTEM PRIVATE ${OPENGL_INCLUDE_DIR})
target_link_libraries(GLFWDemo ${OPENGL_gl_LIBRARY})

cmake_minimum_required(VERSION 3.10)
project(app C CXX)

set(CMAKE_CXX_STANDARD 14)

add_executable(app main.cc)

find_package(glfw3 3.2 REQUIRED)
target_link_libraries(app glfw)
find_package(OpenGL REQUIRED)
# These variables are set by importing OpenGL
target_include_directories(app PUBLIC ${OPENGL_INCLUDE_DIR})
#target_link_libraries(app ${OPENGL_gl_LIBRARY})
target_link_libraries(app ${OPENGL_LIBRARIES})

find_package (Threads)
target_link_libraries (app ${CMAKE_THREAD_LIBS_INIT})

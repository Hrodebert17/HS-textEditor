cmake_minimum_required(VERSION 3.12)

project(gtk)

file(GLOB SRC src/*.cpp)
add_executable(main ${SRC})

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)
link_directories( main ${GTK3_LIBRARY_DIRS})
add_compile_options(main ${GTK3_CFLAGS_OTHER})
include_directories(main ${GTK3_INCLUDE_DIRS})
target_link_libraries(main ${GTK3_LIBRARIES})
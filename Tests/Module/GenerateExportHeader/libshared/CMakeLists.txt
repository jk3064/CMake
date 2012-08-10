
cmake_minimum_required(VERSION 2.8)

project(libshared)

include(GenerateExportHeader)

add_compiler_export_flags()

set(CMAKE_INCLUDE_CURRENT_DIR ON)

add_library(libshared SHARED libshared.cpp)

configure_file(libshared.cpp libshared.c COPYONLY)

add_library(libshared_c SHARED libshared.c)

generate_export_header(libshared)

export(TARGETS libshared libshared_c FILE Targets.cmake)

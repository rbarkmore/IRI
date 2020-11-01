cmake_minimum_required(VERSION 3.13)

project(IRI2001 VERSION 1.0 DESCRIPTION "IRI-2001" LANGUAGES Fortran)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/bin)

add_library(iri2001_lib STATIC "")

add_subdirectory(src)

add_executable(test_iri2001 src/iritest.for)

target_link_libraries(test_iri2001 LINK_PUBLIC iri2001_lib)

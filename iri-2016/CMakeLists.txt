cmake_minimum_required(VERSION 3.13)

project(IRI2016 VERSION 1.0 DESCRIPTION "IRI-2016" LANGUAGES Fortran)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/bin)

add_library(iri2016_lib STATIC "")

add_subdirectory(src)

add_executable(test_iri2016 src/iritest.for)

target_link_libraries(test_iri2016 LINK_PUBLIC iri2016_lib)

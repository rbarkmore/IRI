cmake_minimum_required(VERSION 3.13)

project(IRI1990 VERSION 1.0 DESCRIPTION "IRI-1990" LANGUAGES Fortran)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/bin)

add_library(iri1990_lib STATIC "")

add_subdirectory(src)

add_executable(test_iri1990 src/irid12.for)

target_link_libraries(test_iri1990 LINK_PUBLIC iri1990_lib)

add_custom_command(TARGET test_iri1990 POST_BUILD
 COMMAND ${CMAKE_COMMAND} -E copy_directory
 ${CMAKE_SOURCE_DIR}/data-1990/ $<TARGET_FILE_DIR:test_iri1990>)

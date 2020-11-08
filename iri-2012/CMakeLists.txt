cmake_minimum_required(VERSION 3.13)

project(IRI2012 VERSION 1.0 DESCRIPTION "IRI-2012" LANGUAGES Fortran)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/bin)

option(BUILD_IRITEST  "Enable this to build iri-test" ON)
option(BUILD_ORBIT    "Enable this to build orbit" ON)
option(BUILD_ORBITMAX "Enable this to build orbitmax" ON)

#******

add_library(iri2012_lib STATIC "")

add_subdirectory(src)

#******
if(BUILD_IRITEST)
#message("msg: BUILD_IRITEST is enabled.")

add_executable(test_iri2012 src/iritest.for)

target_link_libraries(test_iri2012 LINK_PUBLIC iri2012_lib)

add_custom_command(TARGET test_iri2012 POST_BUILD
 COMMAND ${CMAKE_COMMAND} -E copy_directory
 ${CMAKE_SOURCE_DIR}/data-2012/ $<TARGET_FILE_DIR:test_iri2012>)

endif(BUILD_IRITEST)

#******
if(BUILD_ORBIT)
#message("msg: BUILD_ORBIT is enabled.")

add_executable(orbit_iri2012 src/iriorbit.for)

target_link_libraries(orbit_iri2012 LINK_PUBLIC iri2012_lib)

add_custom_command(TARGET orbit_iri2012 POST_BUILD
 COMMAND ${CMAKE_COMMAND} -E copy_directory
 ${CMAKE_SOURCE_DIR}/data-2012/ $<TARGET_FILE_DIR:orbit_iri2012>)

endif(BUILD_ORBIT)

#******
if(BUILD_ORBITMAX)
#message("msg: BUILD_ORBITMAX is enabled.")

add_executable(orbitmax_iri2012 src/iriorbitmax.for)

target_link_libraries(orbitmax_iri2012 LINK_PUBLIC iri2012_lib)

add_custom_command(TARGET orbitmax_iri2012 POST_BUILD
 COMMAND ${CMAKE_COMMAND} -E copy_directory
 ${CMAKE_SOURCE_DIR}/data-2012/ $<TARGET_FILE_DIR:orbitmax_iri2012>)

endif(BUILD_ORBITMAX)


cmake_minimum_required(VERSION 3.13)

project(IRI2007 VERSION 1.0 DESCRIPTION "IRI-2007" LANGUAGES Fortran)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/bin)

option(BUILD_IRITEST  "Enable this to build iri-test" ON)
option(BUILD_AKEBONO  "Enable this to build Akebono" ON)
option(BUILD_IMAZ     "Enable this to build IMAZ" ON)

#******

add_library(iri2007_lib STATIC "")

add_subdirectory(src)

#******
if(BUILD_IRITEST)
#message("msg: BUILD_IRITEST is enabled.")

add_executable(test_iri2007 src/iritest.for)

target_link_libraries(test_iri2007 LINK_PUBLIC iri2007_lib)

add_custom_command(TARGET test_iri2007 POST_BUILD
 COMMAND ${CMAKE_COMMAND} -E copy_directory
 ${CMAKE_SOURCE_DIR}/data-2007/ $<TARGET_FILE_DIR:test_iri2007>)

endif(BUILD_IRITEST)

#******
if(BUILD_AKEBONO)
#message("msg: BUILD_AKEBONO is enabled.")

add_executable(akebono src/Te-plasmasphere-akebono/akebono_te.for)

endif(BUILD_AKEBONO)

#******
if(BUILD_IMAZ)
#message("msg: BUILD_IMAZ is enabled.")

add_executable(imaz src/IMAZ/imaztest.for src/IMAZ/iri_imaz.for)

endif(BUILD_IMAZ)


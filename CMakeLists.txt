cmake_minimum_required ( VERSION 3.5.2 )

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/CMake" ${CMAKE_MODULE_PATH})

project ( SerialPrinter C CXX )

set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/Build)

set(SOURCE_FILES
  "src/Main.cpp")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin2)

add_subdirectory( nanogui)

source_group( "Source" FILES ${SOURCE_FILES} )

include_directories("${CMAKE_SOURCE_DIR}/nanogui/include/")
include_directories(${NANOGUI_EXTRA_INCS})
add_definitions(${NANOGUI_EXTRA_DEFS})




add_executable( SerialPrinter ${SOURCE_FILES} )

target_link_libraries(SerialPrinter nanogui ${NANOGUI_EXTRA_LIBS})

#target_include_directories( SerialPrinter PUBLIC Include "${CMAKE_SOURCE_DIR}/nanogui/include/")
                                                         #"${CMAKE_SOURCE_DIR}/nanogui/ext/eigen"
                                                         #"${CMAKE_SOURCE_DIR}/nanogui/ext/glfw/include"
                                                         #"${CMAKE_SOURCE_DIR}/nanogui/ext/glad/include"
                                                         #"${CMAKE_SOURCE_DIR}/nanogui/ext/nanovg/src"
                                                         #"${CMAKE_SOURCE_DIR}/nanogui/ext/coro"
                                                         #"${CMAKE_SOURCE_DIR}/nanogui/ext/pybind11")



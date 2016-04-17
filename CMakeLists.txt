cmake_minimum_required(VERSION 3.0.2 FATAL_ERROR)
project(EXAMPLE)

find_package(SWIG REQUIRED)
include(${SWIG_USE_FILE})

find_package(PythonLibs)

set(CMAKE_SWIG_FLAGS "")

include_directories(
    ${PYTHON_INCLUDE_PATH}
    ${PROJECT_SOURCE_DIR}
    ${PROJECT_SOURCE_DIR}/include
    )

add_subdirectory(src)

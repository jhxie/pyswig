cmake_minimum_required(VERSION 3.0.2 FATAL_ERROR)
project(EXAMPLE)

find_package(SWIG REQUIRED)
find_package(PythonLibs REQUIRED)

include(${SWIG_USE_FILE})

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_SWIG_FLAGS "")

file(GLOB EXAMPLE_SWIG_INTERFACE ${PROJECT_SOURCE_DIR}/include/*.i)

# the "-includeall" flag ensures anything in "%inline %{ %}" block
# will be executed properly
set_source_files_properties(
    ${EXAMPLE_SWIG_INTERFACE}
    PROPERTIES C ON
    SWIG_FLAGS "-includeall"
    )

include_directories(
    ${PYTHON_INCLUDE_PATH}
    ${PROJECT_SOURCE_DIR}/include
    )

add_subdirectory(src)

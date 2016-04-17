FILE(GLOB EXAMPLE_SWIG_INTERFACE *.i)
swig_add_module(example python ${EXAMPLE_SWIG_INTERFACE} example.c)
swig_link_libraries(example ${PYTHON_LIBRARIES})

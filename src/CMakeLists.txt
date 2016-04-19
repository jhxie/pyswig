swig_add_module(example python ${EXAMPLE_SWIG_INTERFACE} example.c)
swig_link_libraries(example ${PYTHON_LIBRARIES})

execute_process(COMMAND python3 -c
    "from distutils.sysconfig import get_python_lib; print(get_python_lib())"
    OUTPUT_VARIABLE PYTHON_SITE_PACKAGES OUTPUT_STRIP_TRAILING_WHITESPACE)
install(TARGETS _example DESTINATION ${PYTHON_SITE_PACKAGES})
install(FILES ${CMAKE_BINARY_DIR}/src/example.py
    DESTINATION ${PYTHON_SITE_PACKAGES})

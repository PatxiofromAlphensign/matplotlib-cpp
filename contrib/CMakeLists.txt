cmake_minimum_required(VERSION 3.7)
project (MatplotlibCPP_Test)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(${PYTHONHOME})
include_directories(${PYTHONHOME}/Lib/site-packages/numpy/core/include)
set(PYTHONFULLHOME ${LPYTHONHOME}/config-3.8-x86_64-linux-gnu)
link_directories(${PYTHONFULLHOME})

add_definitions(-DMATPLOTLIBCPP_PYTHON_HEADER=Python.h)

# message(STATUS "*** dump start cmake variables ***")
# get_cmake_property(_variableNames VARIABLES)
# foreach(_variableName ${_variableNames})
#         message(STATUS "${_variableName}=${${_variableName}}")
# endforeach()
# message(STATUS "*** dump end ***")

set(CMAKE_CXX_COMPILER g++)
#set(CMAKE_CXX_FLAGS ${PYTHONFULLHOME}/libpython3.8.a)
set(CMAKE_CXX_FLAGS -lpython3.8)
add_compile_options(${PYTHONFULLHOME}/libpython3.8.a)

add_executable(minimal ${CMAKE_CURRENT_SOURCE_DIR}/../examples/minimal.cpp)

# add_executable(basic ${CMAKE_CURRENT_SOURCE_DIR}/../examples/basic.cpp)
# add_executable(modern ${CMAKE_CURRENT_SOURCE_DIR}/../examples/modern.cpp)
# add_executable(animation ${CMAKE_CURRENT_SOURCE_DIR}/../examples/animation.cpp)
# add_executable(nonblock ${CMAKE_CURRENT_SOURCE_DIR}/../examples/nonblock.cpp)
# add_executable(xkcd ${CMAKE_CURRENT_SOURCE_DIR}/../examples/xkcd.cpp)
# add_executable(bar ${CMAKE_CURRENT_SOURCE_DIR}/../examples/bar.cpp)

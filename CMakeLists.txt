cmake_minimum_required(VERSION 3.18)

project(pybind11example)

if(NOT PYTHON_EXECUTABLE)
    message(FATAL_ERROR "Please specify PYTHON_EXECUTABLE with -DPYTHON_EXECUTABLE=python.exe")
endif()

include(FetchContent)
FetchContent_Declare(
    pybind11
    GIT_REPOSITORY https://github.com/pybind/pybind11
    GIT_TAG        v2.6.1
)
FetchContent_MakeAvailable(pybind11)

pybind11_add_module(${PROJECT_NAME} pybind11example.cpp)
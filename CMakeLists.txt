# CMake minimum required version
cmake_minimum_required(VERSION 3.12)

# Set project name
set(PROJECT_NAME W7500P_FW)

#Set project informations
project(${PROJECT_NAME} C)

set(CMAKE_C_STANDARD 11)


# Set the project root directory if it's not already defined, as may happen if
# the tests folder is included directly by a parent project, without including
# the top level CMakeLists.txt.
if(NOT DEFINED IOLIB_DIR)
    set(IOLIB_DIR ${CMAKE_SOURCE_DIR}/W7500P_FW/ioLibrary)
    message(STATUS "IOLIB_DIR = ${IOLIB_DIR}")
endif()

if(NOT DEFINED PERIPH_DIR)
    set(PERIPH_DIR ${CMAKE_SOURCE_DIR}/W7500P_FW/Libraries/W7500x_stdPeriph_Driver)
    message(STATUS "PERIPH_DIR = ${PERIPH_DIR}")
endif()

if(NOT DEFINED CMSIS_DIR)
    set(CMSIS_DIR ${CMAKE_SOURCE_DIR}/W7500P_FW/Libraries/CMSIS)
    message(STATUS "CMSIS_DIR = ${CMSIS_DIR}")
endif()

if(NOT DEFINED EXAMPLE_DIR)
    set(EXAMPLE_DIR ${CMAKE_SOURCE_DIR}/W7500P_FW/Projects/Peripheral_Examples)
    message(STATUS "EXAMPLE_DIR = ${EXAMPLE_DIR}")
endif()

if(NOT DEFINED SYSTEM_W7500X_DIR)
    set(SYSTEM_W7500X_DIR ${CMAKE_SOURCE_DIR}/W7500P_FW/Libraries/CMSIS/Device/WIZnet/W7500)
    message(STATUS "SYSTEM_W7500X_DIR = ${SYSTEM_W7500X_DIR}")
endif()

if(NOT DEFINED LIB_DIR)
    set(LIB_DIR ${CMAKE_SOURCE_DIR}/W7500P_FW/Libraries)
    message(STATUS "LIB_DIR = ${LIB_DIR}")
endif()

# Hardware-specific examples in subdirectories:
add_subdirectory(${IOLIB_DIR})
add_subdirectory(${PERIPH_DIR})
add_subdirectory(${CMSIS_DIR})
add_subdirectory(${EXAMPLE_DIR})
add_subdirectory(${SYSTEM_W7500X_DIR})
add_subdirectory(${LIB_DIR})



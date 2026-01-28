cmake_minimum_required(VERSION 4.0)

project(TemperatureTaker
    VERSION 0.0.1
    DESCRIPTION "Embedded application which shows the temperature"
    LANGUAGES C CXX ASM
)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")

add_subdirectory(coco)
add_subdirectory(src)


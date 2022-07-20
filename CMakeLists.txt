cmake_minimum_required(VERSION 3.12)

include(pico_sdk_import.cmake)

project(fixmath)

# Initialize the SDK
pico_sdk_init()

add_library(${PROJECT_NAME}
        ${CMAKE_CURRENT_SOURCE_DIR}/src/fix16_exp.c
        ${CMAKE_CURRENT_SOURCE_DIR}/src/fix16_sqrt.c
        ${CMAKE_CURRENT_SOURCE_DIR}/src/fix16_trig.c
        ${CMAKE_CURRENT_SOURCE_DIR}/src/fix16.c
        ${CMAKE_CURRENT_SOURCE_DIR}/src/fract32.c
        ${CMAKE_CURRENT_SOURCE_DIR}/src/uint32.c
)

target_include_directories(${PROJECT_NAME} PRIVATE include)

target_link_libraries(${PROJECT_NAME} pico_stdlib)


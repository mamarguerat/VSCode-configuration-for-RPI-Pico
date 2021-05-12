cmake_minimum_required(VERSION 3.12.0)

include(pico_sdk_import.cmake)
project(pico-projects)
pico_sdk_init()

add_executable(Blink main.cpp)
target_link_libraries(Blink pico_stdlib)
pico_add_extra_outputs(Blink)

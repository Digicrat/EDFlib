cmake_minimum_required (VERSION 2.8.8)
project (EDFLib)
set(CMAKE_C_FLAGS "-Wall -Wextra -Wsign-conversion -D_LARGEFILE64_SOURCE -D_LARGEFILE_SOURCE")

include_directories(.)

add_library(EDFLib edflib.c edflib.h)


add_executable(sine_generator sine_generator.c)
target_link_libraries(sine_generator EDFLib)
target_link_libraries(sine_generator m)

add_executable(sweep_generator sweep_generator.c)
target_link_libraries(sweep_generator EDFLib)
target_link_libraries(sweep_generator m)

add_executable(test_edflib test_edflib.c)
target_link_libraries(test_edflib EDFLib)
target_link_libraries(test_edflib m)

add_executable(test_generator test_generator.c)
target_link_libraries(test_generator EDFLib)
target_link_libraries(test_generator m)


cmake_minimum_required(VERSION 3.15)
project(test_package)

find_package(Snappy REQUIRED CONFIG)

add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} PRIVATE Snappy::snappy)
target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_11)

add_executable(${PROJECT_NAME}_c test_package.c)
target_link_libraries(${PROJECT_NAME}_c PRIVATE Snappy::snappy)

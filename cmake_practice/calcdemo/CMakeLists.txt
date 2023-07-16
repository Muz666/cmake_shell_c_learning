cmake_minimum_required(VERSION 3.0)
project(CALC)
set(SRC_LIST 
        ${PROJECT_SOURCE_DIR}/src/add.c
        ${PROJECT_SOURCE_DIR}/src/sub.c
        ${PROJECT_SOURCE_DIR}/src/mult.c
        ${PROJECT_SOURCE_DIR}/src/div.c)
set(EXECUTABLE_OUTPUT_PATH ../bin)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)
file(GLOB MAIN_SRC ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)
file(GLOB MAIN_HEAD ${CMAKE_CURRENT_SOURCE_DIR}/include/*.h)
include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(${PROJECT_SOURCE_DIR}/lib)
add_library(calc STATIC ${MAIN_SRC})
add_library(calc_d SHARED ${SRC_LIST})
link_libraries(calc)
add_executable(app ./src/main.c)
# target_link_libraries(calc)

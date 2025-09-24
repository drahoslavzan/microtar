cmake_minimum_required(VERSION 3.31)
project(microtar C)

set(CMAKE_C_STANDARD 90)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -fPIC -pedantic -Wall -Wextra")
set(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -O0 -g")
set(CMAKE_C_FLAGS_RELEASE "${CMAKE_C_FLAGS_RELEASE} -DNDEBUG -O3")

set(PUB_HEADERS
    src/microtar.h
)

add_library(microtar STATIC
    src/microtar.c

    ${PUB_HEADERS}
)

target_include_directories(microtar PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/src
)
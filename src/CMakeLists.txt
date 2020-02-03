cmake_minimum_required(VERSION 3.1)
project("png2rex")

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED on)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread -O3 -Wall -Wpedantic -march=native -mtune=native -g")

add_executable(png2rex main.cpp PngLoader.cpp REXSpeeder.cpp)

# We depend upon zlib
find_package(ZLIB REQUIRED)
if (ZLIB_FOUND)
	include_directories(${ZLIB_INCLUDE_DIRS})
	target_link_libraries(png2rex ${ZLIB_LIBRARIES})
endif()

# We also depend upon libpng
find_package(PNG REQUIRED)
include_directories(${PNG_INCLUDE_DIRS})
target_link_libraries(png2rex ${PNG_LIBRARIES})


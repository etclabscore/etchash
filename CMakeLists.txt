cmake_minimum_required(VERSION 2.8.7)
project(etchash)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/modules/")
set(ETHHASH_LIBS etchash)

if (WIN32 AND WANT_CRYPTOPP)
	add_subdirectory(cryptopp)
endif()

add_subdirectory(src/libetchash)

add_subdirectory(src/benchmark EXCLUDE_FROM_ALL)
add_subdirectory(test/c)

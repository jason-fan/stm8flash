cmake_minimum_required(VERSION 2.8)
project(stm8flush)

if(UNIX)
	set(CMAKE_C_COMPILER cc)
	set(CMAKE_C_FLAGS "--std=gnu99 --pedantic -Wall")
	
	file(GLOB SRC ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)
	add_executable(stm8flush ${SRC})
	target_link_libraries(stm8flush usb-1.0)

	add_library(espstlink "src/libespstlink.c" "src/libespstlink.h")
else()
	message(STATUS "not unix")
	endif()


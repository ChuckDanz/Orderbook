cmake_minimum_required(VERSION 3.16)

if(UNIX AND EXISTS "/usr/bin/g++")
	set(CMAKE_CXX_COMPILER "/usr/bin/g++")
endif()

project(Orderbook LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

message(STATUS "C++ compiler: ${CMAKE_CXX_COMPILER}")

add_executable(orderbook src/main.cpp)
target_compile_features(orderbook PRIVATE cxx_std_20)

set_target_properties(orderbook PROPERTIES
	RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)

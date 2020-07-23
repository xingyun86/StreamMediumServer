# CMakeList.txt : CMake project for StreamMediaServer, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

set(project_name UsageEnvironment)
project(${project_name})

include_directories(
	${CMAKE_CURRENT_SOURCE_DIR}/include
	${CMAKE_SOURCE_DIR}/LiveFiveFiveFive/GroupSock/include
)
file(GLOB SOURCES "*.cpp" "*.c") 

# Add source to this project's library.
add_library(${project_name} STATIC ${SOURCES})

# TODO: Add tests and install targets if needed.

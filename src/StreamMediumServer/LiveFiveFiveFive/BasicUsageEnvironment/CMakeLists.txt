# CMakeList.txt : CMake project for StreamMediaServer, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

set(project_name BasicUsageEnvironment)
project(${project_name})

include_directories(
	${CMAKE_CURRENT_SOURCE_DIR}/include
	${CMAKE_SOURCE_DIR}/LiveFiveFiveFive/GroupSock/include
	${CMAKE_SOURCE_DIR}/LiveFiveFiveFive/UsageEnvironment/include
)
link_directories(
	${CMAKE_BINARY_DIR}/LiveFiveFiveFive/UsageEnvironment
)
file(GLOB SOURCES "*.cpp" "*.c") 

# Add source to this project's library.
add_library(${project_name} STATIC ${SOURCES})

target_link_libraries(${project_name}
PRIVATE UsageEnvironment
)
# TODO: Add tests and install targets if needed.

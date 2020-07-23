# CMakeList.txt : CMake project for StreamMediaServer, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Add source to this project's executable.
add_executable (StreamMediumServer "StreamMediumServer.cpp" "StreamMediumServer.h")

if(MSVC)
#SET_TARGET_PROPERTIES(${project_name} PROPERTIES LINK_FLAGS ${ADMIN_LEVEL})
endif(MSVC)
# TODO: Add tests and install targets if needed.

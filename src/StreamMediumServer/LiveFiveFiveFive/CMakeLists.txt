# CMakeList.txt : CMake project for StreamMediaServer, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Add source to this project's executable.
add_subdirectory("libressl-3.1.1")
add_subdirectory("UsageEnvironment")
add_subdirectory("GroupSock")
add_subdirectory("BasicusageEnvironment")
add_subdirectory("liveMedia")
add_subdirectory("WindowsAudioInputDevice")
add_subdirectory("hlsProxy")
add_subdirectory("mediaServer")
add_subdirectory("proxyServer")
add_subdirectory("testProgs")

# TODO: Add tests and install targets if needed.

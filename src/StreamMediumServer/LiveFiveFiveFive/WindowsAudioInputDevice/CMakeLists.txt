# CMakeList.txt : CMake project for StreamMediaServer, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

set(project_name WindowsAudioInputDevice)
project(${project_name})

include_directories(
	${CMAKE_CURRENT_SOURCE_DIR}
	${CMAKE_SOURCE_DIR}/LiveFiveFiveFive/BasicUsageEnvironment/include
	${CMAKE_SOURCE_DIR}/LiveFiveFiveFive/UsageEnvironment/include
	${CMAKE_SOURCE_DIR}/LiveFiveFiveFive/GroupSock/include
	${CMAKE_SOURCE_DIR}/LiveFiveFiveFive/liveMedia/include
	${CMAKE_SOURCE_DIR}/LiveFiveFiveFive/libressl-3.1.1/include
)
link_directories(
	${CMAKE_BINARY_DIR}/LiveFiveFiveFive/BasicUsageEnvironment
	${CMAKE_BINARY_DIR}/LiveFiveFiveFive/UsageEnvironment
	${CMAKE_BINARY_DIR}/LiveFiveFiveFive/GroupSock
	${CMAKE_BINARY_DIR}/LiveFiveFiveFive/liveMedia
	${CMAKE_BINARY_DIR}/LiveFiveFiveFive/libressl-3.1.1/ssl
	${CMAKE_BINARY_DIR}/LiveFiveFiveFive/libressl-3.1.1/tls
	${CMAKE_BINARY_DIR}/LiveFiveFiveFive/libressl-3.1.1/crypto
)
set(RESSL_LIBS re_tls_static re_ssl_static re_crypto_static)
file(GLOB SOURCES "*.cpp" "*.c") 

IF(MSVC)
set(MSVC_LIBS winmm)
ELSE(MSVC)
set(MSVC_LIBS)
ENDIF(MSVC)
# Add source to this project's executable.
add_executable(${project_name}-nomixer "showAudioInputPorts.cpp" "WindowsAudioInputDevice_common.cpp" "WindowsAudioInputDevice_noMixer.cpp")

target_link_libraries(${project_name}-nomixer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)
# Add source to this project's executable.
add_executable(${project_name}-mixer "showAudioInputPorts.cpp" "WindowsAudioInputDevice_common.cpp" "WindowsAudioInputDevice_mixer.cpp")

target_link_libraries(${project_name}-mixer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)
# TODO: Add tests and install targets if needed.

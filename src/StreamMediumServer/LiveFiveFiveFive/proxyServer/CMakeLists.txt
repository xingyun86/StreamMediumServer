# CMakeList.txt : CMake project for StreamMediaServer, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

set(project_name proxyServer)
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

# Add source to this project's library.
add_executable(${project_name} ${SOURCES})

target_link_libraries(${project_name}
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
)
# TODO: Add tests and install targets if needed.

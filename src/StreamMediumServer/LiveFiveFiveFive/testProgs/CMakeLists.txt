# CMakeList.txt : CMake project for StreamMediaServer, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

set(project_name testProgs)
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
add_executable(${project_name}-mikeyParse "mikeyParse.cpp")

target_link_libraries(${project_name}-mikeyParse
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-MPEG2TransportStreamIndexer "MPEG2TransportStreamIndexer.cpp")

target_link_libraries(${project_name}-MPEG2TransportStreamIndexer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-playCommon "playCommon.cpp" "openRTSP.cpp")

target_link_libraries(${project_name}-playCommon
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-registerRTSPStream "registerRTSPStream.cpp")

target_link_libraries(${project_name}-registerRTSPStream
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-sapWatch "sapWatch.cpp")

target_link_libraries(${project_name}-sapWatch
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testAMRAudioStreamer "testAMRAudioStreamer.cpp")

target_link_libraries(${project_name}-testAMRAudioStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testDVVideoStreamer "testDVVideoStreamer.cpp")

target_link_libraries(${project_name}-testDVVideoStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testGSMStreamer "testGSMStreamer.cpp")

target_link_libraries(${project_name}-testGSMStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testH264VideoStreamer "testH264VideoStreamer.cpp")

target_link_libraries(${project_name}-testH264VideoStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testH264VideoToHLSSegments "testH264VideoToHLSSegments.cpp")

target_link_libraries(${project_name}-testH264VideoToHLSSegments
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testH264VideoToTransportStream "testH264VideoToTransportStream.cpp")

target_link_libraries(${project_name}-testH264VideoToTransportStream
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testH265VideoStreamer "testH265VideoStreamer.cpp")

target_link_libraries(${project_name}-testH265VideoStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testH265VideoToTransportStream "testH265VideoToTransportStream.cpp")

target_link_libraries(${project_name}-testH265VideoToTransportStream
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMKVSplitter "testMKVSplitter.cpp")

target_link_libraries(${project_name}-testMKVSplitter
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMKVStreamer "testMKVStreamer.cpp")

target_link_libraries(${project_name}-testMKVStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMP3Receiver "testMP3Receiver.cpp")

target_link_libraries(${project_name}-testMP3Receiver
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMP3Streamer "testMP3Streamer.cpp")

target_link_libraries(${project_name}-testMP3Streamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG1or2AudioVideoStreamer "testMPEG1or2AudioVideoStreamer.cpp")

target_link_libraries(${project_name}-testMPEG1or2AudioVideoStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG1or2ProgramToTransportStream "testMPEG1or2ProgramToTransportStream.cpp")

target_link_libraries(${project_name}-testMPEG1or2ProgramToTransportStream
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG1or2Splitter "testMPEG1or2Splitter.cpp")

target_link_libraries(${project_name}-testMPEG1or2Splitter
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG1or2VideoReceiver "testMPEG1or2VideoReceiver.cpp")

target_link_libraries(${project_name}-testMPEG1or2VideoReceiver
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG1or2VideoStreamer "testMPEG1or2VideoStreamer.cpp")

target_link_libraries(${project_name}-testMPEG1or2VideoStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG2TransportReceiver "testMPEG2TransportReceiver.cpp")

target_link_libraries(${project_name}-testMPEG2TransportReceiver
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG2TransportStreamer "testMPEG2TransportStreamer.cpp")

target_link_libraries(${project_name}-testMPEG2TransportStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG2TransportStreamSplitter "testMPEG2TransportStreamSplitter.cpp")

target_link_libraries(${project_name}-testMPEG2TransportStreamSplitter
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG2TransportStreamTrickPlay "testMPEG2TransportStreamTrickPlay.cpp")

target_link_libraries(${project_name}-testMPEG2TransportStreamTrickPlay
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testMPEG4VideoStreamer "testMPEG4VideoStreamer.cpp")

target_link_libraries(${project_name}-testMPEG4VideoStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testOggStreamer "testOggStreamer.cpp")

target_link_libraries(${project_name}-testOggStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testOnDemandRTSPServer "testOnDemandRTSPServer.cpp")

target_link_libraries(${project_name}-testOnDemandRTSPServer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testRelay "testRelay.cpp")

target_link_libraries(${project_name}-testRelay
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testReplicator "testReplicator.cpp")

target_link_libraries(${project_name}-testReplicator
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testRTSPClient "testRTSPClient.cpp")

target_link_libraries(${project_name}-testRTSPClient
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-testWAVAudioStreamer "testWAVAudioStreamer.cpp")

target_link_libraries(${project_name}-testWAVAudioStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)

# Add source to this project's executable.
add_executable(${project_name}-vobStreamer "vobStreamer.cpp")

target_link_libraries(${project_name}-vobStreamer
PRIVATE BasicUsageEnvironment
PRIVATE UsageEnvironment
PRIVATE GroupSock
PRIVATE liveMedia
PRIVATE ${RESSL_LIBS}
PRIVATE ${MSVC_LIBS}
)
# TODO: Add tests and install targets if needed.

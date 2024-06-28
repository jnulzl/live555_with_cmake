add_executable_for_live555(testMP3Streamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testMP3Streamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testMPEG1or2VideoStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG1or2VideoStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testMPEG1or2AudioVideoStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG1or2AudioVideoStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testMPEG2TransportStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG2TransportStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testMPEG4VideoStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG4VideoStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testH264VideoStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testH264VideoStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testH265VideoStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testH265VideoStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testDVVideoStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testDVVideoStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testWAVAudioStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testWAVAudioStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testAMRAudioStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testAMRAudioStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testMKVStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testMKVStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testOggStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/testOggStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(vobStreamer
        "${CMAKE_CURRENT_SOURCE_DIR}/vobStreamer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testMP3Receiver
        "${CMAKE_CURRENT_SOURCE_DIR}/testMP3Receiver.cpp"
)

add_executable_for_live555(testMPEG1or2VideoReceiver
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG1or2VideoReceiver.cpp"
)

add_executable_for_live555(testMPEG2TransportReceiver
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG2TransportReceiver.cpp"
)

add_executable_for_live555(sapWatch
        "${CMAKE_CURRENT_SOURCE_DIR}/sapWatch.cpp"
)
##########
add_executable_for_live555(testRelay
        "${CMAKE_CURRENT_SOURCE_DIR}/testRelay.cpp"
)

add_executable_for_live555(testReplicator
        "${CMAKE_CURRENT_SOURCE_DIR}/testReplicator.cpp"
)

add_executable_for_live555(testOnDemandRTSPServer
        "${CMAKE_CURRENT_SOURCE_DIR}/testOnDemandRTSPServer.cpp;${CMAKE_CURRENT_SOURCE_DIR}/announceURL.cpp"
)

add_executable_for_live555(testRTSPClient
        "${CMAKE_CURRENT_SOURCE_DIR}/testRTSPClient.cpp"
)

add_executable_for_live555(openRTSP
        "${CMAKE_CURRENT_SOURCE_DIR}/openRTSP.cpp;${CMAKE_CURRENT_SOURCE_DIR}/playCommon.cpp"
)

add_executable_for_live555(playSIP
        "${CMAKE_CURRENT_SOURCE_DIR}/playSIP.cpp;${CMAKE_CURRENT_SOURCE_DIR}/playCommon.cpp"
)

add_executable_for_live555(testH264VideoToHLSSegments
        "${CMAKE_CURRENT_SOURCE_DIR}/testH264VideoToHLSSegments.cpp"
)

add_executable_for_live555(testMPEG1or2Splitter
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG1or2Splitter.cpp"
)

add_executable_for_live555(testMPEG1or2ProgramToTransportStream
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG1or2ProgramToTransportStream.cpp"
)

add_executable_for_live555(testH264VideoToTransportStream
        "${CMAKE_CURRENT_SOURCE_DIR}/testH264VideoToTransportStream.cpp"
)

add_executable_for_live555(testH265VideoToTransportStream
        "${CMAKE_CURRENT_SOURCE_DIR}/testH265VideoToTransportStream.cpp"
)

add_executable_for_live555(MPEG2TransportStreamIndexer
        "${CMAKE_CURRENT_SOURCE_DIR}/MPEG2TransportStreamIndexer.cpp"
)

add_executable_for_live555(testMPEG2TransportStreamTrickPlay
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG2TransportStreamTrickPlay.cpp"
)

add_executable_for_live555(registerRTSPStream
        "${CMAKE_CURRENT_SOURCE_DIR}/registerRTSPStream.cpp"
)

add_executable_for_live555(testMKVSplitter
        "${CMAKE_CURRENT_SOURCE_DIR}/testMKVSplitter.cpp"
)

add_executable_for_live555(testMPEG2TransportStreamSplitter
        "${CMAKE_CURRENT_SOURCE_DIR}/testMPEG2TransportStreamSplitter.cpp"
)

add_executable_for_live555(mikeyParse
        "${CMAKE_CURRENT_SOURCE_DIR}/mikeyParse.cpp"
)

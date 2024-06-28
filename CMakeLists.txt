cmake_minimum_required(VERSION 3.15)
project(live555)

if(NOT WITH_OPENSSL)
    set(WITH_OPENSSL OFF)
endif()

if(NOT LINUX_ARCH)
    set(LINUX_ARCH aarch64) # aarch64, arm
endif()

set(CMAKE_COLOR_MAKEFILE ON)
set(CMAKE_VERBOSE_MAKEFILE ON)
##############Set output directory##############
if(NOT OUTPUT_DIRECTORY)
    set(OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/${LINUX_ARCH}/static)
    if(BUILD_SHARED_LIBS)
        set(OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/${LINUX_ARCH}/shared)
    endif()
endif()
file(MAKE_DIRECTORY ${OUTPUT_DIRECTORY})
set(EXECUTABLE_OUTPUT_PATH ${OUTPUT_DIRECTORY})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY  ${EXECUTABLE_OUTPUT_PATH})
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY  ${EXECUTABLE_OUTPUT_PATH})
set(LIBRARY_OUTPUT_PATH ${EXECUTABLE_OUTPUT_PATH})

### ref: https://github.com/rgaufman/live555/issues/45
if(NOT ${CMAKE_CXX_STANDARD} OR ${CMAKE_CXX_STANDARD} LESS 20)
    message(STATUS "No C++20 standard specified, using -DNO_STD_LIB=1 flag for https://github.com/rgaufman/live555/issues/45")
    add_compile_definitions(NO_STD_LIB=1)
endif()

# ref: config.{os-platform}
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-deprecated -DSOCKLEN_T=socklen_t -DNO_SSTREAM=1 -D_LARGEFILE_SOURCE=1 -D_FILE_OFFSET_BITS=64")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${CMAKE_C_FLAGS} -Wall -DBSD=1")

# OpenSSL(ADD YOUR OWN OPENSSL ARCH)
if(WITH_OPENSSL)
    set(OpenSSL_ROOT_DIR ${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/openssl)
    set(OpenSSL_INC_DIR ${OpenSSL_ROOT_DIR}/include)
    set(OpenSSL_LIB_DIR ${OpenSSL_ROOT_DIR}/lib/${LINUX_ARCH})
else()
    add_compile_definitions(NO_OPENSSL=1)
endif()

include_directories(
        ${OpenSSL_INC_DIR}
        /usr/local/include
        ${PROJECT_SOURCE_DIR}/liveMedia/include
        ${PROJECT_SOURCE_DIR}/groupsock/include
        ${PROJECT_SOURCE_DIR}/UsageEnvironment/include
        ${PROJECT_SOURCE_DIR}/BasicUsageEnvironment/include
)
link_directories(${OpenSSL_LIB_DIR})

file(STRINGS    ${CMAKE_CURRENT_SOURCE_DIR}/liveMedia/include/liveMedia_version.hh _tmp  REGEX "^#define[ \t]+LIVEMEDIA_LIBRARY_VERSION_STRING[ \t]+")
string(REPLACE "#define LIVEMEDIA_LIBRARY_VERSION_STRING	" "" LIVE555_VERSION_TMP ${_tmp})
string(REPLACE "\"" "" LIVE555_VERSION ${LIVE555_VERSION_TMP})
message(STATUS "live555 version : ${LIVE555_VERSION}")
set(LIVE555_SOVERSION 1)

set(liveMedia_name liveMedia)
set(groupsock_name groupsock)
set(BasicUsageEnvironment_name BasicUsageEnvironment)
set(UsageEnvironment_name UsageEnvironment)

# Used for testProgs、mediaServer、proxyServer and hlsProxy directories
macro(add_executable_for_live555 exe_name src_all)
    message(STATUS "Adding executable : ${exe_name}")
    add_executable(${exe_name}
            ${src_all}
    )

    target_include_directories(${exe_name} PRIVATE
            ${CMAKE_CURRENT_SOURCE_DIR}
    )

    target_link_libraries(${exe_name} PRIVATE
            ${liveMedia_name}
            ${groupsock_name}
            ${BasicUsageEnvironment_name}
            ${UsageEnvironment_name}
    )
    if(WITH_OPENSSL)
        target_link_libraries(${exe_name} PRIVATE
                ssl
                crypto
        )
    endif()
endmacro()

## libraries
add_subdirectory(liveMedia)
add_subdirectory(groupsock)
add_subdirectory(UsageEnvironment)
add_subdirectory(BasicUsageEnvironment)

## executables
add_subdirectory(testProgs)
add_subdirectory(mediaServer)
add_subdirectory(proxyServer)
add_subdirectory(hlsProxy)
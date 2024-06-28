file(GLOB _tmp ${CMAKE_CURRENT_SOURCE_DIR}/*.c*)
set(src_all ${src_all} ${_tmp})
add_library(${BasicUsageEnvironment_name}
        ${src_all}
)

target_include_directories(${BasicUsageEnvironment_name} PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

if(${BUILD_SHARED_LIBS})
    set_target_properties(${BasicUsageEnvironment_name} PROPERTIES VERSION ${LIVE555_VERSION} SOVERSION ${LIVE555_SOVERSION})
endif()
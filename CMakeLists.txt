cmake_minimum_required(VERSION 2.8)
project(silk)

set(SRC_BASE_PATH ${CMAKE_CURRENT_SOURCE_DIR})

set(SEC_HEADER_PATH ${SRC_BASE_PATH}/interface)
set(SRC_PATH ${SRC_BASE_PATH}/src)


include_directories(
        ${SEC_HEADER_PATH}
        ${SRC_PATH}
)

aux_source_directory(${SRC_BASE_PATH}/src SRC_SILK)

set(SHARED_SRCS
        ${SRC_SILK}
        )

add_library(
        ${PROJECT_NAME}
        STATIC
        ${SHARED_SRCS}
)
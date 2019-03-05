cmake_minimum_required(VERSION 3.0)
project(log.c)

option(LOGC_COLORFUL "enable colorful logging" ON)

if (LOGC_COLORFUL)
    add_definitions(-DLOG_USE_COLOR)
endif (LOGC_COLORFUL)

list(APPEND SRCS
    src/log.c
    )

add_library(${PROJECT_NAME} STATIC ${SRCS})
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)


cmake_minimum_required(VERSION 3.7)
project(Filters)

include(filters.cmake)

add_definitions(-fpic)

SET(OPENJPEG_SRC
        ${CMAKE_CURRENT_SOURCE_DIR}/reframe_jp2.c
        ${CMAKE_CURRENT_SOURCE_DIR}/dec_j2k.c
        ${CMAKE_CURRENT_SOURCE_DIR}/img.c
)

SET(OPENJPEG_LIB
      ${CMAKE_CURRENT_SOURCE_DIR}/lib/libopenjp2.a
)

SET(OPENJPEG_INC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

add_filter(openjpeg
        "${OPENJPEG_SRC}"
        "${OPENJPEG_LIB}"
        []
        GPAC_HAS_JP2
        "${OPENJPEG_INC}"
        ""
        "1")

project(miniaudio)

add_library(miniaudio STATIC)

target_sources(miniaudio
  PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}/extras/miniaudio_split/miniaudio.h"
  PRIVATE
    "${CMAKE_CURRENT_SOURCE_DIR}/extras/miniaudio_split/miniaudio.c"
)

target_include_directories(miniaudio
  PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}/extras/miniaudio_split/"
)

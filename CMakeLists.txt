project(miniaudio)

add_library(miniaudio STATIC)

if(IOS)
  target_sources(miniaudio
    PUBLIC
      "${CMAKE_CURRENT_SOURCE_DIR}/miniaudio.h"
    PRIVATE
      "${CMAKE_CURRENT_SOURCE_DIR}/extras/ios/miniaudio.m"
  )

  target_include_directories(miniaudio
    INTERFACE
      "${CMAKE_CURRENT_SOURCE_DIR}/"
  )

  target_link_libraries(miniaudio
    PRIVATE
      "-framework AudioToolbox"
      "-framework AVFAudio"
  )
else()
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
endif()

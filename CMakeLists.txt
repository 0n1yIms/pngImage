cmake_minimum_required(VERSION 3.6.0)
project(pngImage)

add_subdirectory(libs/zlib)
add_subdirectory(libs/libpng)

add_library(pngImage STATIC
        ${CMAKE_CURRENT_SOURCE_DIR}/pngImage.h
        ${CMAKE_CURRENT_SOURCE_DIR}/pngImage.cpp
        )
target_include_directories(pngImage PUBLIC 
        ${CMAKE_CURRENT_SOURCE_DIR}
        )
        
target_link_libraries(pngImage libpng)

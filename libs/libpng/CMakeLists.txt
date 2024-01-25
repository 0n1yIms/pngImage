cmake_minimum_required ( VERSION 3.6.0 )

cmake_minimum_required(VERSION 3.6.0)

file (GLOB libpng_SRCS 
        ${CMAKE_CURRENT_SOURCE_DIR}/include/*.h)
file (GLOB libpng_HDRS 
        ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)

set(libpng_INCLUDE ${CMAKE_CURRENT_SOURCE_DIR}/include)

add_library(libpng STATIC ${libpng_SRCS} ${libpng_HDRS})
target_include_directories(libpng PUBLIC
        ${libpng_INCLUDE}
        ${zlib_INCLUDE}
        )
target_link_libraries(libpng zlib)


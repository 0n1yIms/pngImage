cmake_minimum_required(VERSION 3.6.0)
project(pngImage)

set(CMAKE_INSTALL_PREFIX ${CMAKE_SOURCE_DIR}/install)

add_subdirectory(libs/zlib)
add_subdirectory(libs/libpng)
add_subdirectory(PngImage)

# install
install(FILES 
    ${CMAKE_SOURCE_DIR}/PngImage/PngImage.hpp
    DESTINATION include/PngImage
)

install(TARGETS pngImage 
    ARCHIVE DESTINATION lib
)

# for install run cmake --install ./build --config Release --prefix ./install
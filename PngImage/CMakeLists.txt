cmake_minimum_required(VERSION 3.6.0)
project(pngImage)


add_library(pngImage SHARED
        ${CMAKE_CURRENT_SOURCE_DIR}/pngImage.hpp
        ${CMAKE_CURRENT_SOURCE_DIR}/pngImage.cpp
        )
target_include_directories(pngImage PUBLIC 
        ${CMAKE_CURRENT_SOURCE_DIR}
        )
        
target_link_libraries(pngImage libpng)

# install
install(FILES 
    ${CMAKE_CURRENT_SOURCE_DIR}/pngImage.hpp
    DESTINATION include/PngImage
)

install(TARGETS pngImage 
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
    RUNTIME DESTINATION bin
)

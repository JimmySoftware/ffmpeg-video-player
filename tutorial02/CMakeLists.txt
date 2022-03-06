##
# CMake minimum required version for the project.
##
cmake_minimum_required(VERSION 3.11)

##
# tutorial02 C Project CMakeLists.txt.
##
project(tutorial02 C)

##
# Sets the C standard whose features are requested to build this target.
##
set(CMAKE_C_STANDARD 99)

INCLUDE_DIRECTORIES(/usr/local/Cellar/ffmpeg/5.0/include /usr/local/Cellar/sdl2/2.0.20/include)
LINK_DIRECTORIES(/usr/local/Cellar/ffmpeg/5.0/lib /usr/local/Cellar/sdl2/2.0.20/lib)
LINK_LIBRARIES(avcodec avformat swresample swscale SDL2)

##
# Adds tutorial02.c executable target.
##
add_executable(tutorial02 tutorial02.c)


##
# Add subdirectories to the build.
##
add_subdirectory(References/create-window)
add_subdirectory(References/moving-rectangle)
add_subdirectory(References/render-present)
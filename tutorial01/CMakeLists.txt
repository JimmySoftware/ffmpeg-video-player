##
# CMake minimum required version for the project.
##
cmake_minimum_required(VERSION 3.11)

##
# tutorial01 C Project CMakeLists.txt.
##
project(tutorial01 C)

##
# Sets the C standard whose features are requested to build this target.
##
set(CMAKE_C_STANDARD 99)

INCLUDE_DIRECTORIES(/usr/local/Cellar/ffmpeg/5.0/include)
LINK_DIRECTORIES(/usr/local/Cellar/ffmpeg/5.0/lib)
LINK_LIBRARIES(avcodec avformat swresample swscale)

##
# Adds tutorial01.c executable target.
##
add_executable(tutorial01 tutorial01.c)




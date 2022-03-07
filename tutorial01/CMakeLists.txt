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

message(${CMAKE_SYSTEM_NAME})

if (${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    INCLUDE_DIRECTORIES(/usr/local/Cellar/ffmpeg/5.0/include)
    LINK_DIRECTORIES(/usr/local/Cellar/ffmpeg/5.0/lib)
    LINK_LIBRARIES(avcodec avformat swresample swscale)
endif()

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux0")
    INCLUDE_DIRECTORIES(/usr/include/aarch64-linux-gnu/ /home/ubuntu/lib-aarch64-linux-gnu/include/aarch64-linux-gnu/)
    LINK_DIRECTORIES(/usr/lib/aarch64-linux-gnu/)
    LINK_LIBRARIES(avcodec avformat swresample swscale avutil)
endif()

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
    INCLUDE_DIRECTORIES(/home/ubuntu/ffmpeg/ /usr/local/include/SDL2/)
    LINK_DIRECTORIES(/home/ubuntu/ffmpeg/libavformat 
        /home/ubuntu/ffmpeg/libavcodec /home/ubuntu/ffmpeg/libswscale 
        /home/ubuntu/ffmpeg/libswresample /home/ubuntu/ffmpeg/libavutil 
        /home/ubuntu/ffmpeg/libavdevice /home/ubuntu/ffmpeg/libavfilter)
    LINK_LIBRARIES(avcodec avformat avdevice avfilter swresample swscale avutil pthread SDL2 m z)
endif()

##
# Adds tutorial01.c executable target.
##
add_executable(tutorial01 tutorial01.c)




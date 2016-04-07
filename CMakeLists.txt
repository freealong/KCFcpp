cmake_minimum_required(VERSION 2.8)
project(test)

find_package(OpenCV REQUIRED)
FIND_LIBRARY(FFTW3_LIBRARIES NAMES fftw3 libfftw3)

if(NOT WIN32)
ADD_DEFINITIONS("-std=c++0x -O3")
endif(NOT WIN32)

include_directories(src) 
FILE(GLOB_RECURSE sourcefiles "src/*.cpp")
add_executable( KCF ${sourcefiles} )
target_link_libraries( KCF ${OpenCV_LIBS} ${FFTW3_LIBRARIES})





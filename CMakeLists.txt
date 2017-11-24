CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
SET(PROJ_NAME RIC)
PROJECT (${PROJ_NAME})
# AUX_SOURCE_DIRECTORY(. SRC_LIST)
# SET(SRC_LIST testmain.cpp ./SLICSuperpixels/SLIC.cpp)
# MESSAGE(STATUS "source list: " ${SRC_LIST})

ADD_DEFINITIONS(-DWITH_SSE)

set(OpenCV_DIR C:/opencv/build/install)

find_package( OpenCV 3 REQUIRED )

include_directories(${OpenCV_INCLUDE_DIRS} include)

ADD_EXECUTABLE(${PROJ_NAME} main.cpp RIC.cpp SLIC.cpp)

TARGET_LINK_LIBRARIES(${PROJ_NAME} ${OpenCV_LIBS})

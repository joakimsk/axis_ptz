cmake_minimum_required (VERSION 3.4.1)

add_library(axis_ptz_lib STATIC src/ptz.cpp)

FIND_PACKAGE(CURL)
INCLUDE_DIRECTORIES(${CURL_INCLUDE_DIR})
FIND_PACKAGE(BOOST)
INCLUDE_DIRECTORIES(${BOOST_INCLUDE_DIR})


target_include_directories(axis_ptz_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include ${CURL_LIBRARIES} ${BOOST_LIBRARIES})
set(CMAKE_CXX_FLAGS "-std=c++11")

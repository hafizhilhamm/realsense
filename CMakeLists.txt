cmake_minimum_required(VERSION 2.8)

project(realsense)

find_package(realsense2 REQUIRED)
find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )
add_executable(realsense test.cpp)
set_property(TARGET realsense PROPERTY CXX_STANDARD 11)
target_link_libraries(realsense ${DEPENDENCIES})
target_link_libraries(realsense ${realsense2_LIBRARY})
target_link_libraries( realsense ${OpenCV_LIBS} )
# set_target_properties (rs-hello-realsense PROPERTIES FOLDER "Examples")

install(TARGETS realsense RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})

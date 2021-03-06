CMAKE_MINIMUM_REQUIRED(VERSION 3.1.0)
project(CALIB_CAM)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

find_package(OpenCV REQUIRED)
include_directories($(OpenCV_INCLUDE_DIRS))

add_executable(calibrate calib_intrinsic.cpp cxxopts/cxxopts.hpp)
target_link_libraries(calibrate ${OpenCV_LIBS})

add_executable(read read_images.cpp cxxopts/cxxopts.hpp)
target_link_libraries(read ${OpenCV_LIBS})

add_executable(calibrate_stereo calib_stereo.cpp cxxopts/cxxopts.hpp)
target_link_libraries(calibrate_stereo ${OpenCV_LIBS})

add_executable(undistort_rectify undistort_rectify.cpp cxxopts/cxxopts.hpp)
target_link_libraries(undistort_rectify ${OpenCV_LIBS})
cmake_minimum_required(VERSION 2.8.3)
project(robot_odometry)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  nav_msgs
  roscpp
  tf
)

catkin_package(
  CATKIN_DEPENDS nav_msgs roscpp tf
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(odometry_broadcaster src/odometry_broadcaster.cpp)
target_link_libraries(odometry_broadcaster ${catkin_LIBRARIES})

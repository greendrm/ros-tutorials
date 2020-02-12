cmake_minimum_required(VERSION 2.8.3)
project(robot_setup_tf)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  roscpp
  tf
)

catkin_package(
  CATKIN_DEPENDS geometry_msgs roscpp tf
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

add_executable(tf_broadcaster src/tf_broadcaster.cpp)
target_link_libraries(tf_broadcaster ${catkin_LIBRARIES})

add_executable(tf_listener src/tf_listener.cpp)
target_link_libraries(tf_listener ${catkin_LIBRARIES})

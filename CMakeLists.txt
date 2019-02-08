cmake_minimum_required(VERSION 2.8.3)
project(nav_control)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  actionlib_msgs
  geometry_msgs
  message_generation
  std_msgs
  rospy
  tf
)

catkin_python_setup()

add_service_files(
  DIRECTORY srv
  FILES
    MoveTo.srv
)

generate_messages(DEPENDENCIES
  actionlib_msgs
  geometry_msgs
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS
    actionlib_msgs
    geometry_msgs
    message_runtime
    std_msgs
    rospy
    tf
)


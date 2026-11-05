cmake_minimum_required(VERSION 3.0.2)
project(robotic_arm_5dof)

find_package(catkin REQUIRED COMPONENTS
  rospy
  sensor_msgs
  robot_state_publisher
  joint_state_publisher
  joint_state_publisher_gui
  rviz
)

catkin_package()

install(
  DIRECTORY
  urdf
  launch
  rviz
  DESTINATION
  ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

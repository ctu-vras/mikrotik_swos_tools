cmake_minimum_required(VERSION 3.10.2)
project(mikrotik_swos_tools)

find_package(catkin REQUIRED COMPONENTS message_generation std_msgs)

add_message_files(DIRECTORY msg)
generate_messages(DEPENDENCIES std_msgs)

catkin_package(CATKIN_DEPENDS message_runtime std_msgs)

catkin_install_python(PROGRAMS
  nodes/swos_api
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

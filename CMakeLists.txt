cmake_minimum_required(VERSION 2.8)
project(dynamic_reconfigure_advr)

find_package(catkin REQUIRED COMPONENTS roscpp std_msgs)
find_package(Boost REQUIRED COMPONENTS system thread chrono)

include_directories(include ${catkin_INCLUDE_DIRS} ${Boost_INCLUDE_DIRS})

catkin_package(LIBRARIES 
               INCLUDE_DIRS include
               CATKIN_DEPENDS message_runtime std_msgs
               CFG_EXTRAS dynamic_reconfigure-extras.cmake
)


install(DIRECTORY include/dynamic_reconfigure_advr/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
  FILES_MATCHING PATTERN "*.h")


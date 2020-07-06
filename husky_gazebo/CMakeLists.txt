cmake_minimum_required(VERSION 2.8.3)
project(husky_gazebo)

find_package(catkin REQUIRED COMPONENTS roslaunch)

catkin_package()

roslaunch_add_file_check(launch)
catkin_add_env_hooks(60.env-hook
    SHELLS sh DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})

install(
  DIRECTORY urdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
  )

install(
  DIRECTORY launch worlds
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

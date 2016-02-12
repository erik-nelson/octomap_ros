cmake_minimum_required(VERSION 2.8.3)
project(octomap_ros)
find_package(catkin REQUIRED)
catkin_package()

include(ExternalProject)

externalproject_add(octomap_ros
  GIT_REPOSITORY https://github.com/OctoMap/octomap_ros.git
  GIT_TAG 0.3.1
  CMAKE_ARGS -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX} -DSHARED_LIBS=ON
  UPDATE_COMMAND ""
)

install(FILES package.xml DESTINATION share/${PROJECT_NAME})

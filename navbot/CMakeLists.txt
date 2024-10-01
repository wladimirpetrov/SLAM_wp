cmake_minimum_required(VERSION 3.0.2)
project(navbot3_navigation_and_mapping)

## Find catkin macros and libraries
find_package(catkin
  REQUIRED
  COMPONENTS
  turtlesim
)

###################################
## Custom project configuration ##
###################################

## This catkin_package macro is used to generate config files 
catkin_package(
  CATKIN_DEPENDS
  turtlesim
)

#############
## Install ##
#############

## Install Python scripts, ensuring proper functionality 
catkin_install_python(PROGRAMS
  nodes/explore.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

# Install RViz files for visualization
install(
  FILES
  rviz/explore.rviz
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)


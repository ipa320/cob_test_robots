cmake_minimum_required(VERSION 2.8.3)
project(cob_torso_2dof)

find_package(catkin REQUIRED COMPONENTS roslaunch rostest)

catkin_package()

### TESTING ###
if(CATKIN_ENABLE_TESTING)
    roslaunch_add_file_check(launch)
    add_rostest(urdf/test/urdf.test)
endif()

### INSTALL ###
install(DIRECTORY calibration config launch urdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

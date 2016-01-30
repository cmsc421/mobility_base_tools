cmake_minimum_required(VERSION 2.8.3)
project(mobility_base_tools)

find_package(catkin REQUIRED COMPONENTS 
  roslaunch
  rospy
  rqt_gui
  rqt_gui_py
)

catkin_python_setup()

catkin_package()

roslaunch_add_file_check(launch)

install(DIRECTORY launch rviz resource images
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(DIRECTORY scripts/
        DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
        USE_SOURCE_PERMISSIONS
)

install(FILES plugin.xml
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)


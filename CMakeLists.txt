cmake_minimum_required(VERSION 2.8.3)
project(dji_m100_description)

find_package(catkin REQUIRED)

catkin_package(
	CATKIN_DEPENDS 
	joint_state_controller
	robot_state_publisher
	dji_m100_controller_gazebo
)
if(CMAKE_RELEASE_PREFIX STREQUAL "release")
	SET(CMAKE_INSTALL_PREFIX /opt/ros/$ENV{ROS_DISTRO})
	install(DIRECTORY meshes
	  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
	)

	install(DIRECTORY urdf
	  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
	)
endif()


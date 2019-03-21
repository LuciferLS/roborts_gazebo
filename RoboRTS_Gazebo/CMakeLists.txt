cmake_minimum_required(VERSION 2.8.3)

project(roborts_gazebo)

find_package(catkin REQUIRED)



catkin_package()


find_package(roslaunch)

foreach(dir config launch meshes urdf worlds materials)
	install(DIRECTORY ${dir}/
		DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)


# the following code is to place the materials in correct direction
# the place where gazebo puts the models by default
set(GAZEBO_MODEL_PATH $ENV{HOME}/.gazebo)


# to create folder : /home/user/.gazebo/models/my_robot_description
file(MAKE_DIRECTORY ${GAZEBO_MODEL_PATH}/${PROJECT_NAME})
#add_custom_target(COMMAND cmake -E make_directory ${GAZEBO_MODEL_PATH}/${PROJECT_NAME})


# copy my_robot meshes to gazebo models folder


file(GLOB MY_PUBLIC_HEADERS
  "materials/*.png"
)
file(COPY ${MY_PUBLIC_HEADERS} DESTINATION  ${GAZEBO_MODEL_PATH}/${PROJECT_NAME})
file(GLOB MY_PUBLIC_HEADERS
  "materials/*.material"
)
file(COPY ${MY_PUBLIC_HEADERS} DESTINATION  ${GAZEBO_MODEL_PATH}/${PROJECT_NAME})


# install(DIRECTORY materials
#   DESTINATION ${GAZEBO_MODEL_PATH}/${PROJECT_NAME}
#   FILES_MATCHING 
#   #PATTERN "*.dae"
#   PATTERN "*.png"
#   PATTERN "*.material"
# )

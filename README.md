# Gazebo simulation environment (modified from ICRA2018_DJI_RM_AI_Challenge_NJUST)
This repo is a simple simulator wrapper form [`ICRA2018_DJI_RM_AI_CHALLENGE_NJUST`](https://github.com/jackychen227/ICRA2018_DJI_RM_AI_Challenge_NJUST) for single-robot RoboRTS navigation stack simulation.

Special thanks for `jackychen227`.

Please follow this [guide](http://gazebosim.org/tutorials?tut=plugins_model&cat=write_plugin) to import `gazebo_plugins`.

Plugins parameters description in this [doc](https://github.com/KevinLADLee/RoboRTS-Simple-Simulator-Wrapper/blob/master/RoboRTS_Gazebo_Plugins/RoboRTS%20Gazebo%20Plugin.md).

## Software Requirements
	• ROS kinetic (Ubuntu 16.04)
    • Gazebo 7

## Test Platform
	• Intel® Core™ i7-8700k 
	• NVIDIA GeForce GTX 1050
	• OS type: 64-bit

# Important
To load the floor texture, we have to provide path to gazebo resource.
When running the simulation for the first time (or first time after the update), run the following to add the environment variable to your `.bashrc`
```bash
echo "export GAZEBO_RESOURCE_PATH=${HOME}/.gazebo:${GAZEBO_RESOURCE_PATH}" >> ~/.bashrc
```

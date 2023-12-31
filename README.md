# KAL CONTROLLER ROS TOOL

ROS wrapper for the kal_controller package

## What is this package doing?

This ROS wrapper handles all ROS related functionality to call the library implementation of the controller in the kal_controller package.
The provided node will listen to trajectory messages and find the current vehicle pose in the tf tree, convert them to Eigen data types and pass both to the library.
The returned control command will then be converted to a ROS message and published.
Additionally, the wrapper handles the parameters.

## Usage

Include the `controller_node.launch` file in a meta package launching the autonomous stack and set the required parameters.

For testing and development purposes, there is also a standalone launch file available.

## Test

Check out the rostest in the test directory of this package.
It starts the node, publishes a mocked trajectory and vehicle pose and makes sure the computed control commands meets the expectations.
It also makes sure that the trajectory checks are working.

Since testing with ROS can be quite cumbersome, most of the functionality is tested in kal_controller directory.
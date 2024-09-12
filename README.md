# f1tenth2.0_sw_stack
An updated F1Tenth Software Stack for ROS2 Humble

## Installation Pre-Requisites
The ZED SDK must be pre-installed for a succesful build
https://www.stereolabs.com/en-gr/developers

## ROS2 Build
1. Create your workspace folder
2. Run `colcon build` on the empty folder to initialize
3. Create a src folder
4. Clone the repository into the src folder
5. Run `rosdep update`
6. Run `rodep install --from-paths src -i -y`
7. Run `colcon build`

The build should be succesfully completed

## Tips 

Don't forget to `source /opt/ros/humble/setup.bash` if not 
in your `.bashrc` file

In a clean Ubuntu 22.04 some ROS packages might be required. 
Make sure to read the build errors and address them accordingly. 

e.g. On a clean Ubuntu 22.04 asio_cmake_module was missing. 
It can be simply installed through `sudo apt install ros_hubmle_asio_cmake_module`

## Launch Files
There are 4 useful `.launch` files which can be used for testing

1. `f1tenth_stack f1_tenth_gui.launch.py` -> Launches the control and sensors stack
stack together with RViz in order to visualize the sensor input
2. `f1tenth_stack f1_tenth_remote.launch.py` -> Launches the control and sensors stack only.
Helpful for testing the car. 
3. `f1tenth_stack rosbag_record.launch.py` -> Records all topics published in ROS bag format.
Requires either 1 or 2 running already.
4. `f1tenth_stack rosbag_record_no_camera.launch.py` -> Records all other topics except the camera. 

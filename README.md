# IMcoders

## Dependencies
### ROS Kinetic
Link to official site:  
http://wiki.ros.org/kinetic/Installation/Ubuntu  
**NOTE:** The recomended version is _Desktop-Full Install_

### Gazebo (just for simulation)
Link to official site:  
http://wiki.ros.org/simulator_gazebo/Tutorials/StartingGazebo#Installation  
and install the ros packages _ros-kinetic-gazebo-ros-pkgs ros-kinetic-gazebo-msgs ros-kinetic-gazebo-plugins ros-kinetic-gazebo-ros-control_:  
`sudo apt-get install ros-kinetic-gazebo-ros-pkgs ros-kinetic-gazebo-msgs ros-kinetic-gazebo-plugins ros-kinetic-gazebo-ros-control`

## How-to
1. Create a new ROS workspace or use your an existing one  
`mkdir -p ~/imcoders_ws/src`

1. Clone this repo  
`git clone https://github.com/solosito/IMcoders.git ~/imcoders_ws/src/.`

1. Build the code  
Go to the workspace folder  
`cd ~/imcoders_ws`  
then  
`catkin_make`  
or  
`catkin build`  

1. Source the workspace  
`source ~/imcoders_ws/devel/setup.bash`

1. Launch the simulation  
`roslaunch imcoders_control keyboard_teleop.launch`

1. Launch teleop from a new terminal (node you need to source the workspace as before)  
`roslaunch imcoders_gazebo box_robot_gazebo.launch`

1. Launch Rviz (optional)  
`rviz`

## Troubleshooting
### Missing dependencies while building
If you are missing dependencies for any package in this repo, source the workspace and install the missing dependencies for the packages not building:
`source ~/imcoders_ws/devel/setup.bash`
`rosdep install <package_name>`  

for instance:  
`rosdep install imcoders_control`  

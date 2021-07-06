# Turtlebot3-with-SLAM
Use Turtlebot3 with SLAM approach to create and save a map

# These Steps show how to use Turtlebot3 with SLAM approach to create and save a map

Note: You should already have VMware, ubuntu18.04 and installed ROS.

# 1.	Type in the terminal these commands:

#### •	Install ROS 1 on Remote PC:

$ sudo apt update

$ sudo apt upgrade

$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh

$ chmod 755 ./install_ros_melodic.sh 

$ bash ./install_ros_melodic.sh

#### •	Install Dependent ROS 1 Packages:

$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers

#### •	Install TurtleBot3 Packages:

$ sudo apt-get install ros-melodic-dynamixel-sdk

$ sudo apt-get install ros-melodic-turtlebot3-msgs

$ sudo apt-get install ros-melodic-turtlebot3

#### •	Install simulation packages:

$ cd ~/catkin_ws/src/

$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git

$ cd ~/catkin_ws && catkin_make

$ cd

$ source ~/catkin_ws/devel/setup.bash

#### •	Launch the simulation world:

$ export TURTLEBOT3_MODEL=burger

$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

#### •	Launch the SLAM Node (New terminal):

$ export TURTLEBOT3_MODEL=burger

$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

#### •	interact and control the robot (New terminal):

$ export TURTLEBOT3_MODEL=burger

$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

#### Now you should be able to control the robot using the keys WASDX 

#### Explor the map with your robot 

#### •	Save the map:

$ rosrun map_server map_saver -f ~/map

#### We are done ..


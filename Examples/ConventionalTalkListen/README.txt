ROS Tutorial Talker Listener example.

This example was run natively on Ubuntu 14.04

This assume a functioning Ubuntu 14.04 installation with ROS Indigo 

Essential Ros Indigo Setup Steps

sudo apt-get update

sudo apt-get install ros-indigo-desktop-full

set the environment variable to bash

cd ~

to set the encvironment for this shell
source /opt/ros/indigo/setup.bash

but to add this to bash use:
echo "source ~/ros/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
 
Then add python and tools

sudo apt-get install python-rosdep python-wstool ros-indigo-ros

Initialize rosdep

sudo rosdep init

rosdep update

You can use rosbuild or catkin to build so see the tutorial if needed: 
http://wiki.ros.org/ROS/Tutorials/CreatingPackage

Assuming catkin, Essential steps:

mkdir -p ~/catkin_ws/src

cd ~/catkin_ws/src

catkin_init_workspace

Setup the tutorials

catkin_create_pkg beginner_tutorials std_msgs rospy roscpp

cd ~/catkin_ws

catkin_make

Add the workspace to the ROS environment

. ~/catkin_ws/devel/setup.bash

Get the talker and listener scripts (I used python)

roscd beginner_tutorials

mkdir scripts

cd scripts

wget  https://raw.github.com/ros/ros_tutorials/kinetic-devel/rospy_tutorials/001_talker_listener/talker.py

chmod +x talker.py

wget https://raw.github.com/ros/ros_tutorials/kinetic-devel/rospy_tutorials/001_talker_listener/listener.py

chmod +x listener.py

Build the nodes

cd ~/catkin_ws

catkin_make

Open 3 terminals either on the box or via ssh

in the first terminal run:

roscore

in the second:

rosrun beginner_tutorials talker.py

in the third:

rosrun beginner_tutorials listener.py

and assuming no missed steps, unset variables or permission errors,

You have done it!


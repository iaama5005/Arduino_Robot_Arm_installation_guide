# Arduino_Robot_Arm_installation_guide

Ubuntu version 20.04.4
ROS version Noetic



## Create a ROS Workspace: 

type these commands in cmd: 
    
     source /opt/ros/noetic/setup.bash
     mkdir -p ~/catkin_ws/src
     cd ~/catkin_ws/ 
     catkin_make
     source devel/setup.bash
    
ROS workspace is created. 

## install the Arduino Robot Arm Package: 

First-

add the ardunino robot arm package to the src folder.

to do so type these commands in cmd: 

     cd catkin_ws/src/
     sudo apt install git
     git clone https://github.com/smart-methods/arduino_robot_arm
    
Second-

install all the necessary dependencies.

to do so type these commands in cmd: 

     cd catkin_ws
     sudo apt-get install ros-noetic-moveit
     sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
     sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
     sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control

Third-

compile all packages in your src folder.

to do so type this command in cmd: 

     catkin_make
    
## Check your installation: 

Before running anything on ROS you need to set your source setup file. To do so, type this command in cmd: 

    source /home/%USER_NAME%/catkin_ws/devel/setup.bash
    
%USER_NAME% Change it to your local username.

Open the robot arm in rviz.

to do so type this command in cmd: 

    roslaunch robot_arm_pkg check_motors.launch


You can also open the schematic in Moveit or Gazebo: 

Gazebo Method:

    roslaunch robot_arm_pkg check_motors_gazebo.launch


    
Moveit Method: 


    roslaunch moveit_pkg demo.launch
     
 
 
If any of the above method open the schematic without any error, then your installtion is correct.

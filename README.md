# task-2-Turtlebot3-with-SLAM-approach

###  Use Turtlebot3 with SLAM approach to create and save a map


#### the steps that take to do this task : 

 * install ubountu and ROS 
 * install all dependencies required 
 * install turtlebot3 packages
 * set a default turtlebot3 model name 
 * install turtlebot3 simulation packages
 * Launch Simulation World
 * run SLAM node
 * save map


#### this link will help you to do this task [turtlebot3](https://emanual.robotis.com/docs/en/platform/turtlebot3/overview/)

#### step 1: install a ubountu and ROS . 

#### step 2: install all dependencies we need : 

<p><code>$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
</code></p>

#### step 3: install turtlebot3 packages : 


<p><code>$ sudo apt-get install ros-melodic-dynamixel-sdk</code></p>


<p><code>$ sudo apt-get install ros-melodic-turtlebot3-msgs</code></p>


<p><code>$ sudo apt-get install ros-melodic-turtlebot3</code></p>

step 4: set a default TurtleBot3 Model Name:

<p><code>$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc</code></p>

step 5:  install a turtlebot3 simulation package:

<p><code>cd ~/catkin_ws/src/
</code></p>

<p><code>$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
</code></p>


<p><code>$ cd ~/catkin_ws && catkin_make</code></p>


#### step 6: launch simulation world 
- by choosing one of simulation enviroment, but if you want create map with SLAM so choose either 
     TurtleBot3 World or TurtleBot3 House. 
    
- i will choose TurtleBot3 World :

<p><code>$ export TURTLEBOT3_MODEL=waffle
</code></p>
<p><code>$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
</code></p>

- to make a turtlebot 3 mode operate with keyboard , use this command : 

<p><code>$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
</code></p>

#### step 7: run SLAM node :

<p><code>$ export TURTLEBOT3_MODEL=waffle
</code></p>

<p><code>$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
</code></p>


- to run a teleoperation :

<p><code>$ export TURTLEBOT3_MODEL=burger</code></p>

<p><code>$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch</code></p>

#### step 8: save map : 

<p><code>$ rosrun map_server map_saver -f ~/map</code></p>



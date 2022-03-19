# Odometry Generation & Mapping with Cartographer
Cartographer doesn't produce any odometry. So,this code is written to listen to tf tree of cartographer and produce the odometry message as `/odom` topic. This repository contains 2 ros packages for mapping and localization (odometry) using cartographer_ros package.

# RPLIDAR X1/X2 and Cartographer ROS launch 

This node will launch RPLIDAR X1/X2 and cartographer_ros package for mapping only.

## Start RPLidar and Cartographer ROS package

1. Clone the repo as your src directory 
```
cd ~/catkin_ws
git clone https://github.com/ArghyaChatterjee/cartographer_odometry.git
```
2. Perform the setup described in https://github.com/Slamtec/rplidar_ros for rplidar ros repo setup.
3. If you don't have cartographer installed, Run:
```
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src --rosdistro melodic -r -y
```
4. Compile the sub workspace of whole workspace 
```
catkin_make --only-pkg-with-deps cartographer_mapping
```
5. Source your workspace: 
```
source devel/setup.bash
```
6. Start the rplidar and cartographer mapping node: 
```
roslaunch cartographer_mapping mapping.launch
```

# Odometry Generation From Transform Tree

This node will listen to tf tree of cartographer_ros node and publish the transform message to a topic as `/odom` topic.

## Start the Laser Odom from TF package

1. Clone the repo as your src directory 
```
cd catkin_ws
git clone https://github.com/ArghyaChatterjee/cartographer_odometry.git
```
2. If you don't have necessary dependencies installed run 
```
cd catkin_ws
rosdep install --from-paths src --ignore-src --rosdistro melodic -r -y
```
3. Compile the sub workspace of whole workspace 
```
catkin_make --only-pkg-with-deps laser_odom_from_tf
```
4. Source your workspace 
```
source devel/setup.bash
```
5. Make sure that the `tf` publishing node is publishing the transform between desired frame. 
6. Start the odometry listener node from tf tree
```
roslaunch laser_odom_from_tf publish_odom.launch
```

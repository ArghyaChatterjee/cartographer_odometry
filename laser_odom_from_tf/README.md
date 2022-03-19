# Laser Odometry Generation From Transform Tree

This node will listen to tf tree and publish the message to a topic as an odometry message. This work was performed to create a demonstrator of using RPLIDAR X1/X2 with Google Cartographer.

## Start the laser odom from tf 

1. Clone the repo as your src directory `git clone git@github.com:ArghyaChatterjee/cartographer_odometry.git`
2. Initialize and update submodules `git submodule update --init`
3. If you don't have necessary dependencies installed run `rosdep install --from-paths src --ignore-src --rosdistro melodic -r -y` from your workspace
4. Compile the whole workspace `catkin_make --only-pkg-with-deps laser_odom_from_tf`
5. Source your workspace `source devel/setup.bash`
6. Make sure that the `tf` publishing node is publishing the transform between desired frame. 7. Start the odometry node: `roslaunch laser_odom_from_tf publish_odom.launch`




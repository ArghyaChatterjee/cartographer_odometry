# RPLIDAR X1/X2 - Cartographer project

This project was used to create a demonstrator of using RPLIDAR X1/X2 with Google Cartographer.

## Start Cartographer

1. Clone the repo as your src directory `git clone git@github.com:ArghyaChatterjee/cartographer_odometry.git`
2. Initialize and update submodules `git submodule update --init`
3. Perform the setup described in rplidar/README.md
4. If you don't have cartographer installed run `rosdep install --from-paths src --ignore-src --rosdistro melodic -r -y` from your workspace
5. Source your workspace `source devel/setup.bash`
6. Start everything: `roslaunch cartographer_mapping mapping.launch`




# slam_unilidar
Work space of SLAM with unilidar

## Environment
Ubuntu 20.04 + ROS noetic

Additional ROS package is required:
### pcl-conversions
```
sudo apt-get install ros-noetic-pcl-conversions
```

### Eigen
```
sudo apt-get install libeigen3-dev
```


## Build
1. Download this repo 
```
git clone https://github.com/lonelyfluency/slam_unilidar.git
```
2. Build unitree_lidar_ros
```
cd slam_unilidar
cd unitree_lidar_ros
catkin_make
```
3. Build point_lio
```
cd ..
cd point_lio
catkin_make
```

## Use
1. Get your L1 lidar ready.
2. Run unilidar sdk
```
cd unitree_lidar_ros
source devel/setup.bash
sudo chmod 777 /dev/ttyUSB0
roslaunch unitree_lidar_ros run_withou_rviz.launch
```
3. Run point-lio
```
cd point_lio
source devel/setup.bash
roslaunch point_lio_unilidar mapping_unilidar.launch
```

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
cd slam_unilidar
```
2. Build unitree_lidar_ros
```
cd unitree_lidar_ros
catkin_make
```

## Use
1. Power on your L1 lidar and setup
```
cd unitree_lidar_ros
source devel/setup.bash
sudo chmod 777 /dev/ttyUSB0
```
2. Run unilidar sdk
```
roslaunch unitree_lidar_ros run_without_rviz.launch
```
3. Run point-lio/ SLAM module
```
roslaunch point_lio mapping_unilidar.launch
```

## Point cloud
1. After running SLAM, you can find the point cloud of your last SLAM result in point_lio/PCD/scans.pcd
2. You can view your point cloud by
```
pcl_viewer scans.pcd
```

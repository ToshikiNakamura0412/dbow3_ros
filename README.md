# dbow3_ros

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

The ROS package of [DBow3](https://github.com/rmsalinas/DBow3)

## Environment
- Ubuntu 20.04
- ROS Noetic

## Dependencies
- OpenCV
- [DBow3](https://github.com/rmsalinas/DBow3.git)

## Installation
```bash
cd /path/to/catkin_ws/src
git clone https://github.com/ToshikiNakamura0412/dbow3_ros.git --recursive
catkin build dbow3_ros
```

## Demo
```bash
rosrun dbow3_ros demo_general descriptor_name[brisk,surf,orb] image0 image1 ...
```

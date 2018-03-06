# ORB-VINS
ORB-VINS is a real-time SLAM framework for monocular visual-inertial system. Compared with the VINS system, it replaces the optical flow with the ORB feature, which improves the robustness of the whole system against fast movement and large acceleration. This code runs on Linux, and is fully integrated with ROS.

# 1. Prerequisites
1.1 **Ubuntu** and **ROS**
Ubuntu 14.04 16.04.
ROS Indigo, Kinetic. [ROS Installation](http://wiki.ros.org/indigo/Installation/Ubuntu)
additional ROS pacakge
```
    sudo apt-get install ros-YOUR_DISTRO-cv-bridge ros-YOUR_DISTRO-tf ros-YOUR_DISTRO-message-filters ros-YOUR_DISTRO-image-transport
```
also update opencv3 for ROS Kinetic
```
    sudo apt-get install ros-kinetic-opencv3
```

1.2. **Ceres Solver**
Follow [Ceres Installation](http://ceres-solver.org/installation.html), remember to **make install**.
(Our testing environment: Ubuntu 14.04, ROS Indigo, OpenCV 2.4.8, Eigen 3.2.0) 

# 2. Performance on loitor stereo-IMU module
Open three terminals, run the camera, launch the vins_estimator , rviz respectively. 
```
    rosrun loitor_stereo_visensor loitor_stereo_visensor /home/mysunshine/catkin_ws/src/loitor_stereo_visensor/Loitor_VISensor_Setups.txt
```
    roslaunch vins_estimator loitor.launch 
```
    roslaunch vins_estimator vins_rviz.launch
```

# 3. Build ORB-VINS on ROS
Clone the repository and catkin_make:
```
    cd ~/catkin_ws/src
    git clone git@github.com:HKUST-Aerial-Robotics/VINS-Mono.git
    cd ../
    catkin_make
    source ~/catkin_ws/devel/setup.bash

    

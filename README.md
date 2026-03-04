# ORB-SLAM3 with no Pangolin
This repository is a modified version of [ORB_SLAM3](https://github.com/UZ-SLAMLab/ORB_SLAM3)
The main purpose of this modification is to allow for easy and lightweight deployment onto robotics hardware, by removing all visualization code and all dependencies on Pangolin. Pangolin is superfluous for deployment on hardware limited ROS2 robot platforms since it is slow to build and takes up a lot of space. This package is more lightweight, faster to build and should have all the same functionalities. With my ros2 wrapper, odometry data can still be accessed, allowing for seamless use of ORB_SLAM3 as an onboard SLAM algorithm.
Additionally, this package has updated dependencies for C++17, eigen 3.4.0+, Ceres-Solver 2.3 and a newer version of Sophus. To achieve this, minor modifications have been made to the code base, which should hopefully not change the behavior at all.

Tuning the parameters of ORBSLAM3 is still recommended in an install with a visualizer window. The parameters can be easily ported to this version.
--- 

## Modification
- Succesfully tested in **Ubuntu 22.04** and **ROS2 Humble**(with OpenCV 4.5.4 installed automatically alongside ROS2 Humble)
- Update to work with C++17
- Fixed unexpected <span style="color:red">error</span> when start **STEREO** mode with **Rectified** camera type  

## How to build
Clone the repository:
```
git clone https://github.com/JonanaBanana/ORB-SLAM3-No-Pangolin.git ORB_SLAM3
```

Install same required dependencies as original version, but with Ceres Solver 2.3, eigen 3.4 and the ROS2 Humble installation version of OpenCV (4.5.4), no need for a source installation of OpenCV. Then,  
Execute:
```
cd ORB_SLAM3
chmod +x build.sh
./build.sh
```
This will create **libORB_SLAM3.so**  at *lib* folder and the executables in *Examples* folder.

# ORB-SLAM3-STEREO-FIXED
This branch keeps the additions of the main branch with support for newer versions of software. This includes c++17, ceres solver 2.3, Eigen 3.4.0+, ROS2 Humble+, and a new version of Sophus. This branch simply retains pango dependencies to allow for offboard testing and developing. This branch should not be used onboard a drone, as it has overhead which is not needed for actual implementation, only for testing.

This repository is a modified version of [ORB_SLAM3](https://github.com/UZ-SLAMLab/ORB_SLAM3)  

--- 

## Modification
- Succesfully tested in **Ubuntu 22.04** and **ROS2 Humble**(with OpenCV 4.5.4 from base ROS2 Humble installation)
- Update from C++11 to C++17
- Fixed unexpected <span style="color:red">error</span> when start **STEREO** mode with **Rectified** camera type  

## How to build with_pango branch
Clone the repository:
```
git clone -b with_pango https://github.com/JonanaBanana/ORB-SLAM3-No-Pangolin.git ORB_SLAM3
```

Install same required dependencies as original version. Then,  
Execute:
```
cd ORB_SLAM3
chmod +x build.sh
./build.sh
```
This will create **libORB_SLAM3.so**  at *lib* folder and the executables in *Examples* folder.

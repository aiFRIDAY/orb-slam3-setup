# orb-slam3-
Setup and working of orbslamv3

Tested ORB SLAM3 from : https://github.com/UZ-SLAMLab/ORB_SLAM3

Dependencies:
https://github.com/stevenlovegrove/Pangolin
https://docs.opencv.org/master/d7/d9f/tutorial_linux_install.html
http://eigen.tuxfamily.org/index.php?title=Main_Page

Dataset implemented :
Corridor 4 from :https://vision.in.tum.de/data/datasets/visual-inertial-dataset


Some of the troubles i solved during follwing the setup instructions :
-> running build.sh of orbslam3 freezes os.
Edited build.sh : make -j 6  // 6 is just an example , insert number of cores you have.
I had 8gb ram with 8 cores , even then i used sometimes 6 or 4 , still it had some issues , I just restarted and tried a lot of times until it finally worked.
When I repeated the installation 4 seems to work out best for me , still had to reboot twice.

-> Pangolin dependency problems
for pangolin after getting to build directory run  "cmake -DCPP11_NO_BOOST=1 .. " then " make -j "
or just use "cmake .."  and again if freeze occurs use "make -j 4"

-> buid_ros : path not find
when you put ros path in bashrc , dont forget to source it(bashrc) afterwards.
This was the basic step, and the solution was very hard to find

-> make of g20 fails
I just tried cmake g20 in its build directory manually

-> libORBSLAM3.so not found while running tum_vi_examples
There might be problem with orbslam3 build, clean the build and build again.
I had to build multiple times , I deleted the build folder more than 10 times and eventually it was a success build.
Also tried catkin workspace at the ORBSLAM3 folder and tried catkin clean , build process repetition.




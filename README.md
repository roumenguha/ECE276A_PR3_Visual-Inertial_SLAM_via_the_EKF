# Visual-Inertial SLAM via the EKF
 Visual-Inertial SLAM performed with a visual-keypoint and IMU dataset. The visual keypoints were given to us in pixel coordinates, and the problem of feature-matching across frames has been solved for us. The goal of the project is to track the SE(3) state of the vehicle through the map and to use the visual features to correct for the IMU readings, which suffer from noise. Consult my [Project Report](https://github.com/roumenguha/Visual-Inertial_SLAM_via_the_EKF/blob/master/code/ECE276A_PR3_Report_Roumen_Guha.pdf) in the code folder for more background. 
 
 We observe that, in all of the three datasets provided, the EKF performs well at visual-inertial SLAM (provided the guesses of the covariances belonging to the inherent Gaussian movement noise and measurement noise are good). By comparing each raw path (in red) to its corresponding filtered path (in blue), we can see that the localization of the vehicle benefits tremendously from localizing based on visual keypoint tracking. If the Kalman filter is black magic, the EKF is advanced black magic.
 
 Results shown below: 
 
![alt text](https://github.com/roumenguha/Visual-Inertial_SLAM_via_the_EKF/blob/master/code/results/0022.gif "Dataset 22")

 EKF result for dataset 22. We see at timestamp 201 that the path and landmarks are relatively unchanged, and from timesteps 301 and 501, we see that the biggest changes come from rotations. We know from watching the [associated video](https://github.com/roumenguha/Visual-Inertial_SLAM_via_the_EKF/blob/master/0022.avi) that the vehicle moves around blocks, so some streets should be parallel, and streets should all be straight, and this is precisely what we observe in the final map above at timestamp 799.

![alt text](https://github.com/roumenguha/Visual-Inertial_SLAM_via_the_EKF/blob/master/code/results/0027.gif "Dataset 27")

 EKF result for dataset 27. We see at timestamp 101 that the path and landmarks are more deviated at the beginning here than in other datasets, but the filtered path is much cleaner and regular compared to the raw odometry readings. We know from watching the [associated video](https://github.com/roumenguha/Visual-Inertial_SLAM_via_the_EKF/blob/master/0027.avi) that the vehicle returns to its point of origin, and this is precisely what we observe in the final map above at timestamp 1105.

![alt text](https://github.com/roumenguha/Visual-Inertial_SLAM_via_the_EKF/blob/master/code/results/0034.gif "Dataset 34")

 EKF result for dataset 34. We see at timestamp 201 that the path and landmarks are relatively unchanged, and this remains the case until around timestamp 601. However, we see major deviation in timestamp 801, where the vehicle initiates the turn. We know from watching the [associated video](https://github.com/roumenguha/Visual-Inertial_SLAM_via_the_EKF/blob/master/0027.avi) that the vehicle turns relatively sharply, but not to the extent of doing a U-turn, and this is precisely what we observe in the final map above at timestamp 1223.

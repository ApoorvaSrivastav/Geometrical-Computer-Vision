# Dense Stereo Reconstruction:
What is Dense Stereo Reconstruction:

3D point clouds are very useful in robotics for several tasks such as object detection, motion estimation
(3D-3D matching or 3D-2D matching), SLAM, and other forms of scene understanding. Stereo cameras
provide us with a convenient way to generate dense point clouds. Dense here, in contrast to sparse,
means all the image points are used for the reconstruction.

Downloaded the data from [https://drive.google.com/drive/folders/1EIa7cdugvHkC2avCqip4lcwpRieU326_]. It includes a set of rectified and synchronized stereo image pairs from a KITTI sequence, the calibration data, and the absolute ground truth poses of each stereo pair.
The procedure is as follows,
• Generate a disparity map for each stereo pair. 
• Then, using the camera parameters and baseline information generate colored point clouds from
each disparity map. Get the 3D point cloud
Then using iterative PnP perform motion estimation
Using the generated reconstruction from the previous part, synthesized a new image taken by a virtual
monocular camera fixed at any arbitrary position and orientation.Recovered
this pose using an iterative Perspective-from-n-Points (PnP) algorithm.
The steps are as follows,
• Obtained a set of 2D-3D correspondences between the the image and the point cloud. 
• For this set of correspondences compute the total reprojection error 
• Solve for the pose Tk that minimizes this non-linear reprojection error using a Gauss-Newton (GN)
scheme. 
• Register (or transform) all the generated point clouds into the world frame by using the given
ground truth poses.
• Visualized the registered point cloud data, in color. 

Quick Results
---------
Reconstructed 3D Scene
-------------------------
![Reconstruction Video](https://github.com/ApoorvaSrivastav/Geometrical-Computer-Vision/blob/master/Dense-Reconstruction/Dense_Stereo_Recons.gif)

Input Scene Image   
--------------------------
![Input Scene Image](https://github.com/ApoorvaSrivastav/Geometrical-Computer-Vision/blob/master/Dense-Reconstruction/0000000475.png)






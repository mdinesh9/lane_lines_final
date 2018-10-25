# Camera Calibration
### 1. Briefly state how you computed the camera matrix and distortion coefficients. Provide an example of a distortion corrected calibration image.

First, I computed the calibration points using the chessboard images and then applied those points to undistort the road images. The calibration points are object points which are 3D points and image points which are 2D points. 

# Pipeline
1. Provide an example of a distortion-corrected image.

<img href="output_images/undistorted_lane_image.png" title="Undistorted Lane">

[//]: # (Image References)

[image1]: output_images/undistorted_lane_image.png "Undistorted"


2. Describe how (and identify where in your code) you used color transforms, gradients or other methods to create a thresholded binary image. Provide an example of a binary image result.

[//]: # (Image References)

[image2]: ./output_images/combined_binary_image.png "combined_binary"

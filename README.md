[//]: # (Image References)

[image1]: ./output_images/undistorted_lane_image.png "Undistorted"
[image2]: ./output_images/combined_binary_image.png "Combined Binary"
[image3]: ./output_images/perspective_transform.png "Perspective Transform"
[image4]: ./examples/warped_straight_lines.jpg "Warp Example"
[image5]: ./examples/color_fit_lines.jpg "Fit Visual"
[image6]: ./examples/example_output.jpg "Output"
[video1]: ./project_video.mp4 "Video"


# Camera Calibration
### 1. Briefly state how you computed the camera matrix and distortion coefficients. Provide an example of a distortion corrected calibration image.

First, I computed the calibration points using the chessboard images and then applied those points to undistort the road images. The calibration points are object points which are 3D points and image points which are 2D points. 

# Pipeline
1. Provide an example of a distortion-corrected image.


[//]: # (Image References)

![alt text][image1]


2. Describe how (and identify where in your code) you used color transforms, gradients or other methods to create a thresholded binary image. Provide an example of a binary image result.

First I computed the following gradients across x and y direction, magnitude, gradient and combined all these three. Then I extracted S channel from the original image and combined the binary and the s channel.

![alt text][image2]

3. Describe how (and identify where in your code) you performed a perspective transform and provide an example of a transformed image.

Once I got the combined S channel and binary image from step 2. I used that image to detect the corners of the image and applied cv2.getPerspectiveTransform and then applied cv2.warpPerspective

![alt text][image3]



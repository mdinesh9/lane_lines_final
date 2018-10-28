[//]: # (Image References)

[image1]: ./output_images/undistorted_lane_image.png "Undistorted"
[image2]: ./output_images/combined_binary_image.png "Combined Binary"
[image3]: ./output_images/perspective_transform.png "Perspective Transform"
[image4]: ./output_images/lane_curvature.png "Lane Curvature"
[video1]: ./output_videos/project_video_output.mp4 "Video"


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

4. Describe how (and identify where in your code) you identified lane-line pixels and fit their positions with a polynomial?

Once I applied perspective transform, I got the birds eye view of the image. This helps us easily detect the lane lines even if there is any curvature. First I computed the histogram which helps us find the position of the image where the lane lines exist. We will start with these points and detect the rest of the lines using sliding window.

5. Describe how (and identify where in your code) you calculated the radius of curvature of the lane and the position of the vehicle with respect to center.

First I computed the polynomial of each image and then compute the left and right fits. I used these two points to fit them on the image and computed the left and right curvatures. 

6. Provide an example image of your result plotted back down onto the road such that the lane area is identified clearly.

![alt text][image4]

Pipeline (video)

Hyperlink - [click here][video1]

## Discussion
1. Briefly discuss any problems / issues you faced in your implementation of this project. Where will your pipeline likely fail? What could you do to make it more robust?

The problems that I discovered intially were due to the lightning conditions, and shadows. By changing the threshold values, I was able to solve the challenge for the original project video. I also discovered that the challenge related videos had lane lines with varying pixel values when compared with the original project video. I solved this problem by normalizing the pixels. In the harder video, the current code doesn't perform that well. May be, according to my knowledge, applying deep learning techniques like semantic segmentation would help us solve the problem. 

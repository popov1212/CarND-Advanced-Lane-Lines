**Advanced Lane Finding Project**

The goals / steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.


### Camera Calibration

#### 1. Briefly state how you computed the camera matrix and distortion coefficients. Provide an example of a distortion corrected calibration image.

I use a series of chessboard images to calibrate the camera by calling the function of "findChessboardCorners"

### Pipeline (single images)

#### 1. Provide an example of a distortion-corrected image.

I diaplayed an undistorted image

#### 2. Describe how (and identify where in your code) you used color transforms, gradients or other methods to create a thresholded binary image.

I used a combination of the color threshhold and the sobel threshold in x direction to create a binary image.

#### 3. Describe how (and identify where in your code) you performed a perspective transform and provide an example of a transformed image.

I have realized the image perspective transform by calling the function of "cv2.getPerspectiveTransform",

 src = np.float32([[576.475,460.555],
                   [705.625,460.555],
                   [1038.31,674.427],
                   [271.681,674.427]])
    
dst = np.float32([[400,100],
                 [850,100],
                 [850,720],
                 [400,720]])

#### 4. Describe how (and identify where in your code) you identified lane-line pixels and fit their positions with a polynomial?

I pick out the pixels around the left and right lane lines, and try to fit the lane lines by using the np.ployfit()

#### 5. Describe how (and identify where in your code) you calculated the radius of curvature of the lane and the position of the vehicle with respect to center.

I tried to fit the lane lines by the quadratic polynomial. And then calculate the radius of the point which have the maximum y value.

#### 6. Describe how you restore the imamge.

I call the function of cv2.getPerspectiveTransform() to restore the image.

### Discussion

#### 1. Briefly discuss any problems / issues you faced in your implementation of this project.  Where will your pipeline likely fail?  What could you do to make it more robust?

When I apply my pipline one the project_video.mp4, the are some mistakes on detecting the lane lines. 

Maybe modified some parameters and use machine learning method could make this pipline more robust.  

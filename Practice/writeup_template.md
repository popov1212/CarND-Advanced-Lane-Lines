Writeup

1.Camera Calibration
  
  I use a series of chessboard images to calibrate the camera by calling the function of "findChessboardCorners"
  
2.Apply the distortion correction on a image
  
  I diaplayed the undistorted image
  
3.Performed the perspective transformed image
  
  realize the image perspective transform by calling the function of "cv2.getPerspectiveTransform"
  
4.Create a thresholded binary imamge



5.Apply a perspective transform to rectify binary image


6.Draw the line fitted the bundary


7.Calculate the curvature


8.Apply this pipeilne on the video

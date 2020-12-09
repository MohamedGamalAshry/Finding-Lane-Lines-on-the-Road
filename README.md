# **Finding Lane Lines on the Road** 

[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />  

## Overview

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm. In this project lane lines in images were detected using Python and OpenCV.   

To complete the project, all specifications in the [project requirements](https://review.udacity.com/#!/rubrics/322/view) must be met. The goals of this project are the following:
* Develop a software pipeline that finds lane lines on the road which appears on a series of individual images, and later applying the result to a video stream of a real driving car.
* Reflect the project work in a well-written documentation.

The process of development of the pipeline consist of 6 steps:

* Convert the colored images to gray-scaled images
* Apply Gaussian blur for smoothing the images
* Apply Canny Edge Detection algorithm
* Select the Region of Interest (ROI)
* Apply Hough Transform line detection algorithm
* Combine images.

## Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when trying to figure-out the right parameters for the algorithms, as the process of tunning parameters were too much time consuming.

Another potential shortcoming would be the vibration and the stabilization of the drawn line over the lanes as in the final output of test video there were some vibration that needs to be over-comed.

Another shortcoming could be the calculation done to separate and average of the lines to have better processing for the image and the detected lines.


## Suggest possible improvements to your pipeline

A possible improvement would be to added to the stage of processing the images and the video. As during solving the Challenge video, the effect of the sun, shadow and the curvy lane lines should be considered to have a better lane lines detection.

In the advanced parts of the self-driving Nano-Degree program, I will learn more about Kalman filters and it may be applied to have a better lane detection algorithm.



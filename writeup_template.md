# **Finding Lane Lines on the Road** 

## Udacity Self-Driving Engineer Program - First Project

This is the first project in a series of projects that are required to complete the self-driving engineer nano-degree program.

---

**Finding Lane Lines on the Road**
 
The goals / steps of this project are the following:
* Develop a software pipeline that finds lane lines on the road which appears on a series of individual images, and later applying the result to a video stream of a real driving car.
* Reflect the project work in a well-written documentation.

[//]: #====================================

[//]: # (Image References)

[original_Image]: ./test_images/solidWhiteRight.jpg "OriginalImage"

[Gray_Image]: ./Gray_images_output_Part1/solidWhiteRight.jpg "Gray_Image"

[Edged_Image]: ./Edged_images_output_Part1/solidWhiteRight.jpg "Edged_Image"

[Masked_Image]: ./Masked_images_output_Part1/solidWhiteRight.jpg "Masked_Image"

[HoughTransform_Image]: ./Images_HoughTransform_output_Part1/solidWhiteRight.jpg "HoughTransform_Image"

[Combined_Image]: ./Images_with_detected_Lanes_output_Part1/solidWhiteRight.jpg "Combined_Image"

[Part2_Ex1]: ./Images_with_detected_Lanes_output_Part2/solidWhiteRight.jpg "Part2_Ex1"

[Part2_Ex2]: ./Images_with_detected_Lanes_output_Part2/solidYellowCurve2.jpg "Part2_Ex2"

---
[//]: #====================================
### Reflection

### 1. Software Pipeline description

This pipeline consist of 6 steps:

* Convert the colored images to gray-scaled images
* Apply Gaussian blur for smoothing the images
* Apply Canny Edge Detection algorithm
* Select the Region of Interest (ROI)
* Apply Hough Transform line detection algorithm
* Combine images.

In the following example, we can see one of the images that were used to test and develop the pipeline:  

1- The original image of the road  

![original_Image][original_Image] <figcaption> <center>The original Image</center> </figcaption>

2- The colored image is converted to gray-scaled images  

![Gray_Image][Gray_Image] <figcaption> <center>Image after converted to Gray-Scale</center> </figcaption>

3- Then we apply Gaussian blur and the Canny Edge detection algorithm  

![Edged_Image][Edged_Image] <figcaption> <center>Image after applying Gaussian Blur and Canny Edge detection algorithm</center> </figcaption>

4- Applying a Region of Interest to mask the image and limit the shown region to the area that contain the lane lines  

![Masked_Image][Masked_Image] <figcaption> <center>Image after applying a Region of Interest</center> </figcaption>

5- Applying Hough Transform line detection  

![HoughTransform_Image][HoughTransform_Image] <figcaption> <center>Image after applying Hough Transform line detection</center> </figcaption>

6- Combine the original image with the other image that contain the detected lines.  

![Combined_Image][Combined_Image] <figcaption> <center>Image after applying Hough Transform line detection</center> </figcaption>

---

In order to draw a single and solid line on the left and right lanes, I modified the draw_lines() function by separating the lane lines in two groups depending on their slope.

As the left lane lines has a negative slope and the right lane lines has a positive slope.Then by extracting the X and Y coordinates from both lane lines to have a detailed X, and Y points to draw two solid lines over the lane in the area of interest (ROI).

By following the same steps to detect the lane line, we can see the lane detected in the following images:  

![Part2_Ex1][Part2_Ex1] <figcaption> <center>Example 1: Detecting lane lines and drawing solid lines over it</center> </figcaption>


![Part2_Ex1][Part2_Ex1] <figcaption> <center>Example 2: Detecting lane lines and drawing solid lines over it</center> </figcaption>

---

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when trying to figure-out the right parameters for the algorithms, as the process of tunning parameters were too much time consuming.

Another potential shortcoming would be the vibration and the stabilization of the drawn line over the lanes as in the final output of test video there were some vibration that needs to be over-comed.

Another shortcoming could be the calculation done to separate and average of the lines to have better processing for the image and the detected lines.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to added to the stage of processing the images and the video. As during solving the Challenge video, the effect of the sun, shadow and the curvy lane lines should be considered to have a better lane lines detection.

In the advanced parts of the self-driving Nano-Degree program, I will learn more about Kalman filters and it may be applied to have a better lane detection algorithm.
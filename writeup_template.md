# **Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/laneLines_thirdPass.jpg "Grayscale"

---

### Reflection


My pipeline consisted of 6 steps as following:
* First, I converted the images to grayscale
* Then performed gaussian smoothing
* Applied canny edge detection to isolate lanes
* Used Hough Transform to detect lane lines
* Superimposed the lines on original image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by:
* Calculate slope of line then assign it to left or right lane based on the slope
* Calculating slope and center of both lanes
* Find left and right line points by deciding region of interest based on Y-coordinates



![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming is in the presence of curved lanes the lines are not proper.

Another shortcoming could be in the case of non well lit outdoors wherein a lot of segments in lanes could be missed.


### 3. Suggest possible improvements to your pipeline

We can change the condition for slopes to accommodate by segmenting the images into turns and straight roads.

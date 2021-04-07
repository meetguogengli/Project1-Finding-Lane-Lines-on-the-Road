# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./examples/laneLines_thirdPass.jpg "third"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I apply Gaussian Blur to smoothen edges, then I apply Canny Edge Detection on smoothed gray image, then I perform a Hough Transform to find lanes within our region of interest and trace them in red. In the end, I separate the left and right lanes, interpolate line gradients to create two smooth lines.
![alt text][image2]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calling stats.linregress() funciton from statistic library



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the straight line becomes
curving on the road, the algorithms cannot follow the curve which I don't know how to figure this out, maybe we will learn some techniques to address this kind of situation in the later lectures.

Another shortcoming could be the accuracy of detecting lines under shadows could be improved.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to consider expressing lines as second degree polynomials or more for examples such as the challenge video.

Another potential improvement could be to detect lane lines by color in order to have some redundancy.

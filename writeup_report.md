# **Finding Lane Lines on the Road** 

## Writeup Template


---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. 
First, I converted the images to grayscale, then I applied gussian blur to make it less noisy, and detected edge points using Canny edge detection. To igore the irrelevant part, I extracted a four side polygon area, made the rest part black. Finally found the line along with the lane.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by averaging all line segments, so that I have each final representative line for both left and right lane, and then extended them from the bottom to the top of ROI.



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when encountering a sharp turn where ROI is no longer accurate.
And the way to determine one single line make no sence for obvious reason.

Another shortcoming I can think of is lane detection could be affected by the obstacle(say one car is on the lane for a period of time)


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to expand the ROI and instead of fitting a straight line, we can fit a curve to the output the canny detection.

Another potential improvement could be to record the history of the lane, and use previous detected lane to adjust the following one.

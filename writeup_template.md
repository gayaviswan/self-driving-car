# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

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

My pipeline consisted of 5 steps. 

1. Converted the images from rgb to grayscale to make it  easier to find the edges in the image

2. On the grayscaled image, we run the Gaussian blur to reduce image noise and reduce detail.

3. The resulting image is run through canny edge detection to find all the edges in the image

4. Since our interest is finding the lane lines, we find the regions of interest where our lane line falls in the image. The resulting image only contains the part of the image we are interested

5. With interested region identified in the image, we run Hough transform on this to identify the lane lines

Additionally, In order to draw a single line on the left and right lanes, I modified the draw_lines() function to combine the disjoint lines.

The following images shows how the image goes through the various pipeline before detecting the lane lines after joining the disjoint lines.

![alt text][./examples/grayscale_mine.jpg]
![alt text][./examples/gaussian_blur.jpg]
![alt text][./examples/canny_image.jpg]
![alt text][./examples/region_interest_mine.jpg]
![alt text][./examples/hough_image.jpg]

### 2. Identify potential shortcomings with your current pipeline

The current pipeline is not accounted for identifying various light conditions including cloudy days or night time driving. The pipeline also does not account for curves in the road.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...

# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/solidYellowCurve_original.jpg "solidYellowCurve"
[image2]: ./test_images_output/solidYellowCurve_gray.jpg "gray"
[image3]: ./test_images_output/solidYellowCurve_blur.jpg "gaussian-blur"
[image4]: ./test_images_output/solidYellowCurve_canny.jpg "canny edges"
[image5]: ./test_images_output/solidYellowCurve_roi_mask.jpg "region of interest"
[image6]: ./test_images_output/solidYellowCurve_roi_edges.jpg "edges of ROI"
[image7]: ./test_images_output/solidYellowCurve_hough_lines.jpg "hough transform"
[image8]: ./test_images_output/solidYellowCurve_result.jpg "result"


[image9]: ./test_images_output/challenge_Moment-0001-large-03s_roi_mask.jpg "left slope more"
[image10]: ./test_images_output/solidYellowCurve_roi_mask.jpg "isosceles trapezium"


---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 8 steps. 

1. Read an image from a file or from a video clip.


![alt text][image1]

2. Convert the image from RGB to grayscale

![alt text][image2]

3. Do Gaussian Smoothing on the gray image with a Gaussian Filter

![alt text][image3]

4. Perform Canny edge detection

![alt text][image4]

5. Define a region of interest 

![alt text][image5]

6. Mask away the undesired portions of the image

![alt text][image6]

7. Retrieve Hough lines 

![alt text][image7]

8. Consolidate and extrapolate lines and apply them to the original image

![alt text][image8]



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming :

1. It should be defined different ROI(region of interest) for different kind of lane curve:
	a. the default isosceles trapezium in code is always for most of straight road. 

![alt text][image9]

	b. For more curve road like in challenge.mp4, we should define a differnt trapezium with left slop more.

![alt text][image10]

	PS. For some images like in challenge.mp4, the car's hood should be calculated in Region of interest.

Another shortcoming :
	For yellow curve in challenge.mp4, even though I refefined a more slope trapezium, it's hard to draw the lane perfectly. so I searched in internet and found it should be handle this situation with HSV ways.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be : in real environment, the road has different curve, so we need to predict the ROI parameters more accurate, and I think it should be some difficult way.
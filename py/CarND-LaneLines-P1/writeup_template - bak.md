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
[image8]: ./test_images_output/solidYellowCurve_result_img.jpg "result"


---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

1. Read an image from a file or from a video clip.
![alt text][image1]
2. Convert the image from RGB to grayscale
![alt text][image2]
3. Do Gaussian Smoothing on the gray image with a Gaussian Filter
![alt text][image3]
#3. Convert RGB to HSV
#4. Isolate yellow in HSV to produce a yellow mask
#5. Also isolate white in HSV to produce a white mask
#6. Combine yellow and white masks with bitwise OR
#7. Apply combined mask to darkened grayscale with bitwise OR
#8. Apply a slight Gaussian blur
4. Perform Canny edge detection
![alt text][image4]
10. Define a region of interest 
![alt text][image5]
11. Mask away the undesired portions of the image
![alt text][image6]
11. Retrieve Hough lines 
![alt text][image7]
12. Consolidate and extrapolate lines and apply them to the original image
![alt text][image8]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...

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
[image2]: ./output_images/Lines_solidWhiteRight.jpg
[image3]: ./output_images/Lines_solidWhiteCurve.jpg'
[image4]: ./output_images/Lines_solidYellowCurve2.jpg
[image5]: ./output_images/Lines_solidYellowLeft.jpg
[image6]: ./output_images/Lines_whiteCarLaneSwitch.jpg
[image7]: ./output_images/Lines_solidYellowCurve.jpg

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I appllied a gaussian smoothing function with kernel 5. Afterwards I applied the canny edges with thresholds 60 an 185. Then I defined the region of interest of a trapezoid. 
After that I applied the hough function wiht the same parametres from the lessons. The last step is to combine the the lines obtained in the original image.
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by doing the average of all the slopes, getting the highest point and drawing the line to the bottom point.

If you'd like to include images to show how the pipeline works, here is how to include an image: 


![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]
![alt text][image6]
![alt text][image7]

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...

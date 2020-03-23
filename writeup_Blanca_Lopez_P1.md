# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./output_images/Segment_solidWhiteRight.jpg
[image2]: ./output_images/Segment_solidWhiteCurve.jpg
[image3]: ./output_images/Segment_solidYellowCurve2.jpg
[image4]: ./output_images/Segment_solidYellowLeft.jpg
[image5]: ./output_images/Segment_whiteCarLaneSwitch.jpg
[image6]: ./output_images/Segment_solidYellowCurve.jpg
[image7]: ./output_images/Lines_solidWhiteRight.jpg
[image8]: ./output_images/Lines_solidWhiteCurve.jpg
[image9]: ./output_images/Lines_solidYellowCurve2.jpg
[image10]: ./output_images/Lines_solidYellowLeft.jpg
[image11]: ./output_images/Lines_whiteCarLaneSwitch.jpg
[image12]: ./output_images/Lines_solidYellowCurve.jpg

---

## Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I appllied a gaussian smoothing function with kernel 5. 

Afterwards I applied the canny edges with thresholds 50 an 150. 

Next I defined the region of interest of a trapezoid with vertex . 

After that I applied the hough function wiht the same parametres from the lessons. The last step is to combine the the lines obtained in the original image.

Theses are the segments identified:

![alt text][image1]
![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]
![alt text][image6]

In order to draw a single line on the left and right lanes, I did the average of all the slopes, getting the highest point and drawing the line to the bottom point.

![alt text][image7]
![alt text][image8]
![alt text][image9]
![alt text][image10]
![alt text][image11]
![alt text][image12]

### 2. Identify potential shortcomings with your current pipeline

My video is shaky. One of the reasons is because the line drawing is based on a principle that both sides of the line are identified by the canny edge, which it doesnt always happen as seen here:

![alt text][image5]
It can be seen in this image that the left line, at the bottom part, the left edge is missing.

Other issues are that the canny edge identifies as lines things that aren't lines as it can be seen in the 'yellow output' video.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to narrow even more the region of interest but that would not be feasible because drivers dont drive in the middle of the road exactly, they can change lanes, etc. 

Another potential improvement could be to compare both slopes in the lines and stablish that the slope cannot be very different between them. 
In that same direction, we could compare previous frame and stablish the maximum increment between the lines: the frames shouldn't be very different between each other, so we should expect the small differences in the lines.

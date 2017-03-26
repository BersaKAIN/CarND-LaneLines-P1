**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

#### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 
- I converted the images to grayscale.
- I used a gaussian filter with kernel size of 5 to smooth the image.
- I used canny filter to find pixels with big gradient.
- I used a zone mask that will only edges in certain part of the image.
- I used hough to find lines with the following parameters.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

It's not so good at distinguishing lines from the opposite traffic. It is also not that good at distinguish horizon again a lane line.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to utilize the connection between frames. Suppose in frame 1 we find lane lines are in position A. Then in frame 2, the lane lines shouldn't have moved too far away. Here far is dependant on how fast we are driving and the framerate of the camera. So previous lane line position should be used to correct later frames.

Another potential improvement could be to make some confidence score for lane line decision for each of the lane lines.

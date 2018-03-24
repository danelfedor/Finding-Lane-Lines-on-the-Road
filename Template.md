# **Finding Lane Lines on the Road** 

## Writeup Template


---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 
First, I converted the images to grayscale, science grey scale picture is better identify identify the boundaries.

then, I gaussian blur technique to decrease the noise in the image so I can find clearer edges.

Next step, I use canny function find edges of individual item in picture.

And then, I select the region in image that infront of the driving car.

The last step is use Hugh line method to draw lines in picture.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by draw two lines on start and end coordinates. The firstep is calculate the slope and center in each lines, and then seperate the side of line by slope. Coordinates on the y axis is manully choosen to bottom of picture 0.4 hight of picture. The coordinates on the x axis can be calculated by mean slope and mean of x center on each side.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...

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


One potential shortcoming would be what would happen when the car turning the line in the road will be a curve and we have limited the minimal length of lien so most part of line will not be recognized by the hugh line method.

Another shortcoming could be if there is no solid line and the dotted line may be short or some bright spot existed in the road we cannot get a nice mean and slope. 


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use the region = (x_min,x_max) to constraint the line. If the calculate result is over the regoin I will put the boundary of the region instead of calculated redult

Another potential improvement could be to split one solid line each side two 2. The first part will be start to mid point and onher is mid point to end.

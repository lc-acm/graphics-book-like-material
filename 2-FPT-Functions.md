# Chapter 2: FPT Functions

The FPT graphics functions will be new for most of you. FPT stands for "Freshman Programming Toolkit" and is Jeff's version of a graphics library that allows us to draw graphics on most operating systems in C. If you need help downloading FPT to your personal computer, visit [FPT Tutorial](https://github.com/lc-acm/fpt)

## Setting up a window

The first thing you're going to need to do if you want anything to pop up is create a graphics window. One super important note is that you can't do anything else graphics wise until you have initiated a window (so no changing colors or calling functions that use graphics functions until you initilize the window!).  You'll do this by using 

`G_init_graphics(width, height);`  

You can make the window any size but it will be in pixels so think windows around 600-1000 size wise. 

## Making Shapes

Now for the fun stuff! There are plenty of commands for making all types of shapes but we'll go through the most common ones here. First, in order to create a rectangle, you'd use the function

`G_rectangle(x1, y1, width, height);`

You could also make a filled rectangle (using `G_fill_rectangle();`) or a circle. FPT also allows you to make polygons. In order to make a polygon of any size, you need to have an array of all of the x-points and an array of all of the y-points created so the coordinates line up (ie: the 3rd point on the polygon should have the x-value stored in index 2 of its array and the y-value stored in index 2 of its array) AND the number of points in the polygon. That would look like the below syntax.

`G_polygon(x[], y[], numPoints);`

Because making a point would 

## Colors

Making colors is really simple in FPT. It uses the RGB standard of colors from 0-1 so (0, 0, 0) would be black and (1, 1, 1) would be white. 
## Other Useful Tools

## Compiling and Running Programs

# Chapter 2: FPT Functions

The FPT graphics functions will be new for most of you. FPT stands for "Freshman Programming Toolkit" and is Jeff's version of a graphics library that allows us to draw graphics on most operating systems in C. If you need help downloading FPT to your personal computer, visit [FPT Set-Up Tutorial](https://github.com/lc-acm/fpt)

## 2.1 Setting up a window

The first thing you're going to need to do if you want anything to pop up is create a graphics window. One super important note is that you can't do anything else graphics wise until you have initiated a window (so no changing colors or calling functions that use graphics functions until you initilize the window!).  You'll do this by using 

`G_init_graphics(width, height);`  

You can make the window any size but it will be in pixels so think windows around 600-1000 size wise. 

## 2.2 Making Shapes

Now for the fun stuff! There are plenty of commands for making all types of shapes but we'll go through the most common ones here. First, in order to create a rectangle, you'd use the function

`G_rectangle(x1, y1, width, height);`

You could also make a filled rectangle (using `G_fill_rectangle();`) or a circle. FPT also allows you to make polygons. In order to make a polygon of any size, you need to have an array of all of the x-points and an array of all of the y-points created so the coordinates line up (ie: the 3rd point on the polygon should have the x-value stored in index 2 of its own array and the y-value also stored in index 2 of its own array) AND the number of points in the polygon. That would look like the below syntax.

`G_polygon(x[], y[], numPoints);`

The last thing we'll go over here is drawing lines. This is probably the simplest one that can be done by using

`G_line(x1, y1, x2, y2);`

Because making a point on the window (using `G_point(x, y);`)would only make a tiny dot that's almost impossible to see, if you want users to be able to see points you make, you can draw either a little square or circle at that point that only has to be 3 or 4 pixels big. 

## 2.3 Colors

Making colors is really simple in FPT. It uses the RGB standard of colors from 0 to 1 (*not the standard from 0 to 255*) so (0, 0, 0) would be black and (1, 1, 1) would be white. If you want to use other colors you'll need to use a combination of numbers from 0 to 1 for the red, green, and blue values. Here are a few combinations that create some nice colors:

Purple: `G_rgb(0.7, 0.7, 1);`
Pink:   `G_rgb(0.9, 0.4, 0.8);`
Blue:   `G_rgb(0.2, 0.5, 0.8);`
Green:  `G_rgb(0.7, 0.9, 0.7);`

## 2.4 Other Useful Tools

### 2.4.1 Wait keys and clicks
If you aren't careful, the second your program completes it will close the window before you can see what your program actually did. In order to avoid this, you'll need to use wait. This will stop the program from closing or performing another function until a certain amount of time has passed. 

`G_wait(time);`

You can also use a wait key or a wait click. The wait key function is great for making a quit key to end a program (you can use wait key instead of just wait if you want) but it's also great for taking user input and having your program behave a certain way. For example, if you wanted the program to quit when you hit 'q' or if you wanted it to rotate when you hit 'r' you'd have to use a wait key like this

`double key = G_wait_key();`

Keep in mind that this will reference the ascii value on your keyboard, which is the numerical value that the computer assigns to each key on your keyboard, rather than knowing what letter it is so when you're referencing the keys use the character you're trying to reference. Here's an example, if you want for the 'q' key to quit your program then you'd use the following

`double key = G_wait_key();
if(key == 'q'){
  exit(0); }`
  
Using the wait click function will work similarly, but if you want to use the location where the user clicked, it will save the coordinates into an array of size 2. In order to account for this, you'll need to make an array of 2 doubles to store this.

`double place[2];
G_wait_click(place);`

### 2.4.2 Clearing and Quitting
If you're at the beginning of your program or you want to make a blank screen at some point you'll have to use the clear function. This will paint the entire window in the color you last defined using G_rgb() so be careful to reset your color. In order to do this you'll use

`G_clear();`

If you want to end your program at any point and close the graphics window you'll use

`exit(0);`

## 2.5 Compiling and Running Programs
You'll be using the command line quite a bit in class and you'll be compiling and running all of your programs from there. You should be a little familiar with using the command line from CS 1 but this class introduces acom and ./a.out. 

If you're using a personal computer and it's a Mac, you'll need to have XQuartz open in order for this to work and if you're using a Windows computer you'll need to run `export DISPLAY=:0` and have Xming open.  If you're getting a bunch of segmentation faults when you initially try to run your program and it works on one in the lab, this may be your issue. 

Now that you're ready to run a program, use `acom fileName` to compile the program and then `./a.out` to run it. Once you start importing files that your program will be reading, you'll put filenames next to ./a.out, but for now you should be good to go!

## 2.6 A finished product
Here is an example of what a simple program drawing a circle, polygon, and rectangle on a black screen would look like. 

![2-1-shapesCode](/img/0/2-1-shapesCode.png),

Once you run this program from the command line (as shown in the picture above) it will look like this

![2-2-output](/img/0/2-2-output.png),

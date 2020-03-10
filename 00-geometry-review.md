# Chapter 0: Geometry Review

Many of us haven't taken geometry classes since 8th grade. Being a graphics course, CS 367 depends pretty heavily on geometric rules. Let's take some time to go over the very basics.

## 0.1 Basic Trigonometry

A lot of the ways that we can deal with graphical computation depends on trigonometric fuctions - sine, cosine, and tangent.

These are so integral to this course that we're going to define them in painful detail.

### 0.1.1 Definitions

Given a triangle angle as below:

![0-1-triangle](/img/0/0-1-triangle.png), 

Focus on one angle, &theta; :

![0-2-angle](/img/0/0-2-angle.png), 

There are three main functions we care about.

First, the **Sine function** `sin` measures the "height" of the angle. The sine is defined as `sin(&theta;)=(Opposite)/(Hypotenuse)`, as below:

![0-3-sin](/img/0/0-3-sin.png),

Next, the **Cosine function** `cos` measures the "width" of the angle. The cosine is defined as `cos(&theta;)=(Adjacent)/(Hypotenuse)`, as below:
![0-4-cos](/img/0/0-4-cos.png)

Finally, the **Tangent function** `tan` measures the "angular width" of the angle. The tangent is defined as `tan(&theta;)=(Opposite)/(Adjacent)`, as below:
![0-5-tan](/img/0/0-5-tan.png)

Additionally, the tangent of an angle is related to the sine and cosine. tan(&theta;)=(sin(&theta;))/(cos(&theta;))


When in doubt, remember: **SOH CAH TOA:** **S**ine = **O**pposite/**H**ypotenuse, **C**osine = **A**djacent/**H**ypotenuse, and **T**angent = **O**pposite/**A**djacent

### 0.1.2 Circles & Values

In Graphics, you'll be playing around with cirlces A LOT! You'll mostly be using unit circles as shown below:
![0-6-unitCircle](/img/0/0-6-unitCircle.png)

The unit circle (so named because of the radius of 1 unit), connects a lot of our triangle trig math to give us coordinates. It is important to remember that the cosine of a radian point on the unit circle corresponds to the x-value of that point, and that the sine of a radian point corresponds to the y-value.
![0-7-xy](/img/0/0-7-xy.png)

When graphed, the sine and cosine functions create waves that are periodic. These waves are the result of the periodic nature of angles and as you go around the circle, you follow the wave it forms as shown in the animation below:
![0-8-animation](/img/0/trig_anim.gif)

## 0.2 Distance Formula

It's important to have a notion of distance. In this course we will be using something called Euclidian Distance which is defined through the Pythagorean Theorem. When finding the distance between 2 points, you must use something called the distance formula so consider the picture below:
![0-9-euclid](/img/0/0-9-euclid.svg)
![0-9.1-forumla](/img/0/0-9.1-formula.png)

If you have a point 'a' and a point 'b' and you want to find the distance between them, then the distance is the square root of the (difference between the x-values squared + the difference between the y-values squared).  

## 0.3 Transformations

For your first lab, you've probably been asked to spin a unit-cirlce wheel.  The 3 types of transformations we will be describing here fall into the category of Affine transformations (we will describe more later when we get into linear algebra stuff). 
In completing this task, you will need to alter the points on the circle in some way in order to make it spin. Here are some of the most useful tools you'll need to do so.

In this first introduction to affine transformations, we'll be considering the ways that transformations affect points. Because lines and shapes are made up of (infinite) collections of points, shapes, lines, and other objects will be affected the same way as points. You will see plenty of this later on in this course.

### 0.3.1 Translation

The first, and simplest kind of affine transformation is a translation. As its name may suggest to you, a translation moves, or "translates" a point across the X-Y plane. The point will be moved by &Delta; x in the X-direction and  &Delta; y in the Y-direction. Using the common "ordered-pair" notation, a point (x,y) will become (x &Delta; x +, y +&Delta; y) under a translation.

![0-10-translation](/img/0/0-10-translation.png)

### 0.3.2 Rotation

The next kind of affine transformation we're going to care about is a rotation. Rotation of a point is a bit more complex than translation. When we translate, we need to know one thing - how much we want to move each point. On the other hand, when we're rotating a point, we need to know two things: the angle we want to rotate by, and the origin, about which we're rotating. 

To rotate a point (x,y) about an origin (x0, y0), first, connect the point (x,y) to the point (x0,y0). Then, rotate the line you've created by your rotation angle &theta;, keeping the (x0, y0) end fixed. The end of the line will be the new (x,y).

The transformed coordinates of point (x,y) will become (x * cos(&theta;) - y * sin(&theta;), x * cos(&theta;) + y * cos(&theta;))

![0-11-rotation](/img/0/0-11-rotation.png)

### 0.3.3 Scaling

The final kind of transformation we'll consider is a scaling. To think about scaling, we'll need to abandon our thinking about points and start to consider shapes. Consider a polygon with three vertices (a triangle). The vertices are at points (x1,y1), (x2,y2), and (x3,y3). We want to scale this polygon by a factor of *k*. What we do is multiply each coordinate by *k*, to find the new coordinates: (k * x1, k * y1), (k * x2, k * y2), and (k * x3, k * y3)

![0-12-scale]()

## Lab 0: Point on a circle.

You have a point at position (x,y). First, calculate the radius of the circle that point lies on.

Next, think about what transformations you would need to do, in order to make the point propagate around the circle.

Write down some pseudocode that you think will make your point go around the circle. Be as pedantic as you want. Assume that you have the functions `translate(point)`, `rotate(point)`, and `scale(point)`. Remember that you have to bring an object to the center before you can rotate it

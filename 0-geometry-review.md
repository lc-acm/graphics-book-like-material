# Chapter 0: Geometry Review

Many of us haven't taken geometry classes since 8th grade. Being a graphics course, CS 367 depends pretty heavily on geometric rules. Let's take some time to go over the very basics.

## Basic Trigonometry

A lot of the ways that we can deal with graphical computation depends on trigonometric fuctions - sine, cosine, and tangent.

These are so integral to this course that we're going to define them in painful detail.

### Definitions

Given a triangle angle as below:

![0-1-trriangle](), 

Focus on one angle, &theta; :

![0-2-angle](), 

There are three main functions we care about.

First, the **Sine function** `sin` measures the "height" of the angle. The sine is defined as `sin(&theta;)=(Opposite)/(Hypotenuse)`, as below:

![0-3-sin](),

Next, the **Cosine function** `cos` measures the "width" of the angle. The cosine is defined as `cos(&theta;)=(Adjacent)/(Hypotenuse)`, as below:
![0-4-cos]()

Finally, the **Tangent function** `tan` measures the "angular width" of the angle. The tangent is defined as `tan(&theta;)=(Opposite)/(Adjacent)`, as below:
![0-5-tan]()

Additionally, the tangent of an angle is related to the sine and cosine. tan(&theta;)=(sin(&theta;))/(cos(&theta;))


When in doubt, remember: **SOH CAH TOA:** **S**ine = **O**pposite/**H**ypotenuse, **C**osine = **A**djacent/**H**ypotenuse, and **T**angent = **O**pposite/**A**djacent

### Circles & Values

In Graphics, you'll be playing around with cirlces A LOT! You'll mostly be using unit circles as shown below:
![0-6-unitCircle]()

The unit circle (so named because of the radius of 1 unit), connects a lot of our triangle trig math to give us coordinates. It is important to remember that the cosine of a radian point on the unit circle corresponds to the x-value of that point, and that the sine of a radian point corresponds to the y-value.
![0-7-xy]()

When graphed, the sine and cosine functions create waves that are periodic. These waves are the result of the periodic nature of angles and as you go around the circle, you follow the wave it forms as shown in the animation below:
![0-8-animation]()

## Distance Formula

It's important to have a notion of distance. In this course we will be using something called Euclidian Distance which is defined through the Pythagorean Theorem. When finding the distance between 2 points, you must use something called the distance formula so consider the picture below:
![0-9-euclid]()

If you have a point 'a' and a point 'b' and you want to find the distance between them, then the distance is the square root of the (difference between the x-values squared + the difference between the y-values squared).  

## Transformations

For your first lab, you've probably been asked to spin a unit-cirlce wheel.  The 3 types of transformations we will be describing here fall into the category of Affine transformations (we will describe more later when we get into linear algebra stuff). 
In completing this task, you will need to alter the points on the circle in some way in order to make it spin. Here are some of the most useful tools you'll need to do so.

In this first introduction to affine transformations, we'll be considering the ways that transformations affect points. Because lines and shapes are made up of (infinite) collections of points, shapes, lines, and other objects will be affected the same way as points. You will see plenty of this later on in this course.

### Translation

The first, and simplest kind of affine transformation is a translation. As its name may suggest to you, a translation moves, or "translates" a point across the X-Y plane. The point will be moved by &Delta; x in the X-direction and  &Delta; y in the Y-direction. Using the common "ordered-pair" notation, a point (x,y) will become (x &Delta; x +, y +&Delta; y) under a translation.

![0-10-translation]()

### Rotation

### Scaling

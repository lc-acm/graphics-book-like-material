# Chapter 6: The Scan-line and its limitations

This chapter will go over the main concepts for one of your early labs. You should now be familiar with how to click and save points into an array and how to make a polygon from that array of points. Now we'll be taking it a step further and fill up that shape with color (and no you can't just use G_fill_polygon() because you'd be missing the point of this whole thing).

## The Goal

In this lab you'll be building upon your click and save polygons and slowly fill up the polygon created with color. This may sound like a pretty easy task, but it turns out you'll be needing to use skills like finding intersection points and sorting. Your finished program should look like this and the shape can be filled up using a key on the keyboard.

![6-1-finishedProduct](/img/0/6-1-finishedProduct.mov)

## What you'll need to know how to do

### Scan lines

The easiest way to fill up the polygon is going to be "drawing" a bunch of horizontal, invisible scan lines from the bottom of the screen to the very top. As you do this, you have to find if the scan line interersects with a part of the polygon (whether that is directly on one of the points or if it intersects the line created from connecting 2 points) 

### How do I sort through an array (and why do I need to)? 
### How do I find intersection points?
### What do I need to account for?

## Limitations
### What is this convex shape I keep hearing about?

## Why can't I just use fill polygon?

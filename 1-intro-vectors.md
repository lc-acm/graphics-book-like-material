# Chapter 1: Intro to Vectors

For reasons that may not yet be evident to you, the language and laws of something we call *vectors* will be of extreme importance to you throughout this course. Vectors sometimes follow rules that might not be super intuitive, so this document should help iron out the basics of the ways that vectors work in this course (and in general).

## 1.1 What *is* a Vector?

Something that makes vectors espeically confusing is that the definition of a vector changes depending on who you ask. If you ask a physicist, they'll say something like "a vector is a quantity that has a magnitude and a direction", while a mathematician will say "a vector is an object that can be added and scaled", and a computer scientist would say "a vector is a list of numbers". 

These are all true, and are in fact different ways of stating the nature of vectors in ways that are more useful for applications their respective fields. In this course, we're mostly going to focus on the physical interpretation of a vector (magnitude and direction), but we'll spend some time with the other definitions of vectors as well.

The most important thing to remember is that vectors are a mathematical tool that we can use to help us do geometry and physics and (in this course) model and transform objects in a computer simulation.

Another thing that's important to keep on our minds is what we mean when we call something a *scalar*. For us, a *scalar* is just a number (for our purposes, a real number). This term will be useful later on in this chapter.

Let's go back to that physical definition of a vector: **A vector is a thing that has magnitude and direction**. Unpacking that statement a bit, we can think of a vector like an arrow, pointing in a direction, as shown below:

![1-1-arrow]()

We can think about the vector having an action in the direction in which it is pointing. Something important to note is that with vectors, position does not matter. All that matters is magnitude and direction. Both of the vectors shown below are identical, despite their different positioning. 

![1-2-identity]()

While both of our vector examples were two-dimensional, there's nothing special about 2-D vectors (other than we can easily think about them in a computer screen or sheet of paper), and you will frequently be dealing with 3-D or even higher-dimensional vectors. The following image shows a 3-D vector.

![1-3-3d]()

## 1.2 Vector Notation

In order to rigorously talk about vectors in a way that is helpful and meaningful, we need to formalize some notational standards around the way we're going to think about vectors. 

The first thing that we need to wrap our heads around is that there are two main ways we can think of vectors and their shapes. The first, which we've already alluded to, is to think of a vector as its magnitude and its direction. Usually, we call the magnitude *r* and the direction *&theta;*, or sometimes *&phi;*. This is frequently a good way to conceptualize vectors, but mathematical operations are sometimes difficult. 

A key insight is that a vector can be thought of as a set of numbers, each specifying how far to go in each direction. We can think of our vector as not only having an *r* component and a *&theta;* component, but also as having an *x* component and a *y* component. This is summarized in an image below:

![1-4-proj]()

The thing to remember is that if we have a vector in (*r, &theta;*) form, we can always convert to (*x, y*) form with the following relation:

*x* = *r* * cos(&theta;)

*y* = *r* * sin(&theta;)

Similarly, if we have a vector in (*x,y*) form, we can rewrite it in (*r, &theta;*) form with the following relations:

*r*= sqrt(*x^2* + *y^2*)

*&theta;* = arctan(*y*/*x*)

where sqrt() is the square root function, "^2" notation means "squared,"  and arctan() is the inverse tangent function.

Now that we have a good understanding of the way that we can think of vectors, let's talk really specifically about notation. When we have a vector, we usually denote it as a letter with an arrow above it:

![1-5-a]()

When we want to talk about the length of that vector, we use the absolute value symbol. Some people simply leave off the arrow, but this can be confusing, so we'll stay away from that in this course.

![1-6-magnitude]()

Most people use one of three sets of notation to describe vectors: columnar lists, angle brackets, and unit vectors. These are summarized in the image below. 

![1-7-notation]()

Something important to note is that when we use unit vectors, what we're doing is rewriting our vector as a scalar (number)times a unit vector, which is a vector of length one. We usually assign a unit vector to each axis in our vector space, and we denote a vector as a unit vector with a "hat".

For this course, we'll focus on unit vector notation and columnar list notation.

## 1.3 Vector Operations

What good would vectors be if we couldn't manipulate them in ways that follow predictable and useful rules? The answer is absolutely none. In fact, there are several different types of operations we can perform on vectors, most of which are analogous to other things you may have seen before.

### 1.3.1 Addition

The first important operation with vectors is vector addition. There's a geometric rule and a numerical rule for vector multiplication, and they end up saying the same thing in two different ways. Let's start with the geometric interpretation.

Take two vectors, *a* and *b*. To add them, place them tip-to-tail, and the resulting vector *s* (for sum) will be the vector that connects the tail of *a* to the tip of *b*. This rule works in reverse as well. See the image below:

![1-8-geom-add]()

If this feels weird to you, remember that two vectors are identical if their magnitude and orientation are identical, regardless of where their tail starts.

For numerical addition, you can simply add corresponding terms of a vector, as shown below. Note that this only works in *(x,y)* form, not in *(r, &theta;)* form.

![1-9-numeric-add]()

Adding two vectors represents combining the effects of the two vectors. Note that orientation matters. When adding vectors in different directions, somewhat counterintuitive things sometimes occur. See below for some examples:

![1-10-directionality]()

### Multiplication

Multiplication is another frequently used mathematical vector operation. Somewhat confusingly, there are actually three completely different ways to multiply with vectors. Each of them is useful for different reasons.

#### 1.3.2 Scalar Multiplication

The first and most simple means of multiplication involving vectors is called scalar multiplication. As it may sound, scalar multiplication is multiplying a vector by a scalar. The way we do this numerically is to multiply each term of the vector by the scalar. Let's consider vector *a* and scalar *k*:

![1-11-scalar-num]()

As with addition, the scalar multiplication has a geometric interpretation. It lengthens (or shortens) a vector by a factor of *k*, as below:

![1-12-scalar-geom]()

Okay, so we know how to multiply a vector by a scalar. That sounds useful, but do you know what else sounds useful? Multiplying a vector by a vector! We can actually do that in two ways - one is to multiply a vector by a vector to get a scalar, and one is to multiply a vector by a vector to get a vector. Let's cover each of them:

#### 1.3.3 The Dot Product

The *Dot Product* is a way of multiplying a vector by a vector to get a scalar. There are once again, both numerical and geometric interpretations to the dot product. The dot product is especially useful because of one of its mathematical properties. We'll see that soon.

To take the dot product of two vectors *a* and *b*, we multiply corresponding terms and add:

![1-13-dotprod-num]()

It also turns out that dot products have another, equivalent definition, connecting the dot product to the angle between two vectors:

![1-14-dotprod-cos]()

Now, we have a useful definition of an operation! If we know the two vectors, we can figure out how they're relatively oriented.

As an exercise, see if you can figure out which angle makes the dot product 0, and which angle makes the dot product |a| * |b|. Hint: When is the cosine 0? When is the cosine 1?

Like the other operations, the dot product also has a geometric interpretation. The dot product represents the area of the parallelogram spanned by the two vectors:

![1-15-dotprod-polygon]()

#### 1.3.4 The Cross Product

## 1.4 Why Should I Care?

# Chapter 4: Intro to Matrices

Similarly to our chapter about Vectors, this chapter introduces a somewhat obscure mathematical construction that will at some point soon become incredibly important to your graphics education. Enter "The Matrix".

## 4.1 What is a Matrix?

The Matrix is simply a 2-dimensional arrangement of numbers that we can use to easily keep track of certain types of mathematical operatons. Using matrices will be of great help to us when we work with graphical objects, especially vectors. Matrices can be interpreted in a massive number of ways. In this chapter, we're going to discuss several of them, making sure to give a graphics context.

Matrices are made up of columns and rows, and can have any rectangular dimensionality. A matrix, generally speaking, has coordinates starting from the top-leftmost element, increasing to the bottom-right, as shown in the image below.

![4-1-matrix-coords](/img/0/re1i9ogssarmuhjlkzto.png)

We will sometimes refer to an entire column of a matrix as a *column vector* and an entire row of a matrix as a *row vector*. This is because is many circumstances, we can interpret different parts of matrices just this way - as vectors. 

In the vectors chapter, we tried to give geometric interpretation along with our descriptions of the vector operations. In this chapter, that would be somewhat more difficult, because there are so many different important interpretations of matrices. Instead, in this chapter, we will discuss the matrix operations with examples, and then provide various interpretations later.

Matrices are closely related to vectors. If you haven't yet read chapter 1 of this document, please make sure you have a pretty good familiarity with vector math before you read this one. For example, the term "Dot Product" should mean something to you. 

We're going to use a standard notation with our matrices - we're going to call the number of rows in a matrix *m* and the number of columns in a matrix *n*. We're going to generally use round brackets (parentheses) to surround our matrices. We'll also sometimes refer to specific elements of a matrix. For that, we'll use subscripts. The left subscript will be the row and the right subscript will be the column. All of this should look like the image above.

## 4.2 Matrix Operations

Without any further ado, let's get into what we can actually do with these matrices. We can do all kinds of things, just like with vectors. Some of the things are a little bit more complex than with vectors, but trust us, it'll come in handy. We can add matrices, multiply matrices by scalars, and multiply matrices by other matrices.

### 4.2.1 Matrix Scalar Multiplication

First up is matrix-scalar multiplication. To multiply a matrix by a scalar, you simply multiply a each element in that matrix by your scalar. See our example below:

![4-2-scalar-mult](matrix-scalar-multiplication)

### 4.2.2 Matrix Matrix Addition

Next, we will cover matrix-matrix addition. To add two matrices to get a third matrix, the two input matrices must have the same dimensions (both columns and rows). Once you've verified this, you can add the two matrices together by simply adding corresponding terms. So, for matrix A and matrix B, for each position (m,n), Sum(m,n) = A(m,n) + B(m,n). See the image for and example:

![4-3-matrix-addition](matrix-addition)

### 4.2.3 Matrix Vector Multiplication

Now, we're going to get into the complex ones. First, we're going to try to multiply a matrix by a vector. Rather inspiringly, this is called "matrix-vector multiplication". Sometimes, people also refer to this as a matrix "operating on" the vector. When we get into the later sections of this chapter, specifically 4.5 - "matrices as linear operators" and 4.3 - "matrices as transformations", we will cover this more. For now, let's just cover the mechanics of matrix-vector multiplication.

Say you have a matrix *A* and a vector **_b_**. What happens when you multiply *A* * **_b_** ? Perhaps unsurprisingly, a matrix times a vector always yields a vector. 

### 4.2.3 Matrix Matrix Multiplication

### 4.2.4 Identity

## 4.3 Matrices as Transformations

### Effect on Identity

### 4.3.1 Translation Matrices

### 4.3.2 Rotation Matrices

### 4.3.3 Scaling Matrices

## 4.4 Composition of Matrix Operations

## 4.5 Matrices as Linear/Affine Operators

## 4.6 Matrices as Bases


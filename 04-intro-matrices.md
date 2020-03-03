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

To multiply a matrix by a vector, we first need to make sure that what we're doing makes sense. To do this, we make sure that the length of the vector (the number of elements) is equal to the number of columns in the matrix. If it is not, we cannot perform our multiplication.

Then, each element in our resultant vector will be the dot product of our vector with the corresponding row vector of the matrix. For example, see the image below:

![4-4-matrix-vector-multiplication]()

For a 3x3 example, see the image below:

![4-5-matrix-vector-example]()

### 4.2.3 Matrix Matrix Multiplication

Next up, and penultimately, is matrix-matrix multiplication. In matrix-matrix multiplication, you multiply two matrices to get - you guessed it - another matrix. This is the most complex form of matrix multiplication, by far, but also, it's probably the most useful.

To multiply two matrices, first, you need to figure out whether the two matrices can even be multiplied. We do this by examining their dimensionalities. Recall that *m* is the number of rows in a matrix, while *n* is the number of columns in a matrix. Therefore, the "width" of a row is the same thing as the number of columns. Conversely, the "height" of a column is the same thing as the number of rows. When we multiply matrices, we need the width of the rows in the first matrix to be equal to the height of the columns in the second matrix. Therefore, the *n* of the first matrix must be equal to the *m* of the second matrix. See the graphic below for an example:

![4-6-matrix-matrix-compatibility]()

After you know your matrices are compatible for multiplication, you then can move on to the computation. To find the value of each term in your matrix, you take the dot product of the row vector containing it from the first matrix and the column vector from the second matrix. 

For example, if you're trying to figure out the value of the element in position 1-1 of your resultant, you'd take the first row-vector from the first matrix and the first column-vector from the second matrix, and take the dot product of them. The resulting scalar (remember, a scalar is just a number) goes in the 1-1 position of the resultant matrix. To continue, you could then take the dot product of the first row vector of the first matrix with the second column vector of the second matrix. The resultant of that operation would go in the 1-2 position of the resultant matrix. You'd continue, for each row and column in the input matrices.

See the image below for some examples:

![4-7-matrix-matrix-multiplication]()


### 4.2.4 Identity

The *identity* operation is really a special case of the matrix multiplication. We actually have the same operation with normal multiplication of numbers. The idea of an *identity* is that multiplying something by an identity yields itself. With regular numbers, we this works with the special number 1. When you multiply any number by 1, you get that same number back. 

There's something similar with matrices. In that case, what we do is we set up what's called an "identity matrix". The Identity Matrix is composed of zeros everywhere except the diagonal, which has ones. The 3x3 identity matrix is shown below.

![4-8-3x3-identity-matrix]()

Once you have a matrix that looks like the identity matrix you want, you simply can multiply the matrix you're interested in by the identity, and if you did everything right, the same matrix you put in will pop out.

## 4.3 Matrices as Transformations

Remember how earlier, we talked about matrices having several different geometric and mathematical interpretations? The most important one we're going to deal with in this course is a matrix as a transformation. A matrix can "operate on" other mathematical objects as we have discussed above, with the various methods of multiplying a matrix by another object. In this case, we're going to consider points, and the ways that matrices can operate on points to change their location. 

Because there's no good mathematical notation of a "point" that we can operate on with matrices, we're going to represent these points as their "displacement vectors". Imagine you have a point A = (*a, b, c*) and an origin O = (*o1, o2, o3*). The displacement vector from O to A is computed by taking <*a-o1, b-o2, c-o3*>. In most cases, we can set the origin point to O=(*0,0,0*), in which case our displacement vector would simply be <*a,b,c*>. 

Now, the way that we can think of matrices as transformations is to multiply our displacement vector by the matrix. The resultant vector of that multiplication will be a transformed displacement vector, pointing to where the point we care about has been moved. We say that the matrix "transformed" the point from the first displacement vector to the second one, through the multiplication.

The specific type of transformation we care about in this course is called an "Affine Transformation". What that means is a transformation made up of one or a sequence of translations, rotations, or scales of a point or set of points.

To think about how these affine transformations work, the usual tool we use is called a "unit vector". We consider a vector with a magnitude of 1, pointing exactly in the direction of one of our axes. For each axis we have, we generate a vector like this. After that, we transform them with an affine transformation matrix, and see where the transformed unit vector lands.

People will sometimes refer to these unit vectors by many different names - *e_n* vectors, i,j,k, or just using their actual coordinates. We encourage you to google "unit vector notation" to learn more. In this document, we're going to write out the actual unit vectors in their full, three-dimensional (and two-dimensional) form.

Another important note is that for the purposes of this text, we will use the standard "right-handed" coordinates, that is coordinates that follow the right hand rule, described in the vectors chapter.

### 4.3.1 Scaling Matrices

The first, and simplest, transformation matrix type that we care about is a scaling matrix. The scaling matrix, when operating on a vector, will scale the vector, or make it longer. An important difference between scaling matrices and scaling constants is that the scaling matrix can scale a vector by a different constant in different directions, while a scaling scalar (hehe) will always scale a vector by the same amount in every direction of the space the vector inhabits.

The scaling matrix takes a very particular form. Specifically, it's a (possibly differentially) scaled version of the n-dimensional identity matrix. To scale uniformly by a constant, you can simply multiply the constant by the n-dimensional identity matrix. For example:

![4-9-scaled-2x2-identity-matrix]()

Let's see what happens when we multiply the x- and y- unit vectors by this resulting matrix.:

![4-10-scaled-2x2-identity-matrix-unitvectors]()

Now, let's see what happens to another vector after this transformation:

![4-11-scaled-2x2-identity-matrix-transformation]()

What if we differentially scale (have different constants at different points down the diagonal):

![4-12-differential-scaling-2x2]()

As you can see, we can do all kinds of scaling on these vectors.

### 4.3.2 Rotation Matrices

The next transformation we're going to work with are rotations. Recall (from chapter 1) that a rotations represent "rotating" a vector about an origin point. In this case, our origin point is always THE origin (0,0). In two dimensions, the rotation matrix is rather simple. To produce a rotational transformation with angle &theta; , you multiply the 2-d vector by the following matrix:

![4-13-2d-rotation-matrix]()

In three dimensions, unfortunately, there are some complexities that we need to take into account. There are now three possible axes of rotation. Any object (or vector) living in three-dimensional space can rotate around the *x,y* or *z* axes, or any combination thereof. For simplicity's sake, we're only going to cover the X, Y, and Z versions of 3d rotation matrices.

We encourage all of you to derive these matrices yourselves, but for now, we're just going to state them as fact. If you need help figuring out why they make sense, the best thing to do is to just come up with some vectors and multiply them by the rotation matrices, drawing pictures along the way, to make sure that you understand what's going on.

To rotate a 3-dimensional vector around the X-axis, multiply it by the following matrix:

![4-14-3d-x-rotation-matrix]()

To rotate a 3-dimensional vector around the Y-axis, multiply it by the following matrix:

![4-15-3d-y-rotation-matrix]()

To rotate a 3-dimensional vector around the Z-axis, multiply it by the following matrix:

![4-16-3d-z-rotation-matrix]()

### 4.3.3 Translation Matrices

You may have noticed that so far, all of the matrices and vectors we've been dealing with have had matched dimensions. For example, our two-dimensional rotation matrix was 2x2 and the vector representing a 2d point is 2-long. We can do this because rotation and scaling are both examples of something called a *linear transformation.* One important property of a linear transformation is that, in n-dimensional space, it can always be represented by a multiplication of a vector of length n by an nxn matrix. 

Unfortunately, our luck has run out when it comes to translation. Translation is not a linear transformation, but is instead part of a group called *affine transformations*. Fortunately, we're not completely out of options. It turns out that affine transformations can always be represented (in an n-dimensional space) as multiplication of a vector of length n+1 by an n+1xn+1 matrix. 

To translate a vector by (&Delta; x,&Delta; y, &Delta; z), you can multiply it by the following matrix:


![4-17-3d-translation-matrix]()

For another exercise (if you're in the class, you'll have to do this anyways), try to figure out how to use a 4x4 matrix to represent rotations and scaling. You have the tools you need to do so.


## 4.4 Composition of Matrix Operations

So why do we want to do our transformations by multiplying matrices anyways? The most important reason is what we refer to as *composability*. This is the idea that we can do multiple transformations all at once by somehow combining many transformation matrices into one. 

In our case, with matrices, we can do a really simple trick to compose transformations. If you have two matrices, each of which represent a single affine transformation, to compose them and create a matrix that will have the effect of performing one transformation, then another, you can simply multiply the two matrices against each other.

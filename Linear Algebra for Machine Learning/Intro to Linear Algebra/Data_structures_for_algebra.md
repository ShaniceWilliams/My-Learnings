# Tensors

Tensors are machne learning generalisations of vectors and matrices to any number of dimensions.

![Representations of a scalar, vector and a matrix](Images/scalar_vector_matrix.png)

![Table of tensors](Images/tensors.png)

## Scalars

Scalars are single number tensors that have not dimensionality. Denoted as lowercase in italics, they will be typed as integers or floats for example.

In the jupyter notbook that accompanies this course, we see examples of how scalars can be represented in base python, numpy, tensorflow, and pytorch. In each example, we see scalara creation, how to view the type, how you can perform mathematical operations with them, and when shape is asked it is empty as there is no dimensionality.

## Vectors and Vector Transposition

Vector tensors are one dimensional arrays of numbers (made up of scalars). They are usually denoted in lowercase, italics and bold. They are arranged in a specific order and so elements can be accesed by their indices. Vectors can also represent a point in space.

Here is an example of a vector representing a point on a 2D matrix:
![Vector on 2D matrix](Images/vector_on_2d_matrix.png)

### Vector transposition

Vector transposition is when you transform a row vector to a column vector or vice versa. Here is a visual representation of such a transformation: 

![Example of vector Transposition](Images/vector_transposition.png)

Arrays cannot be created in base python (lists are NOT the same as arrays), so you need to use numpy to create the array.

When writing code, you cannot transpose a 1 dimensional vector, but if it is in the format of one row of a matrix (double square brackets), you can use .T to transpose the vector back and forth (example of which is in the code).

Same methods are used to create vector tensors as scalar tensors in pytorch and tensorflow, only difference being the values you use as arguments.
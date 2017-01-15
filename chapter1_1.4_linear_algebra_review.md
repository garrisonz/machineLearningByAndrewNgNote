
==================================
1.4 Linear Algebra Review

1.4.1 Matrices and Vectors
Matrix : Rectangular array of numbers:
[[1, 2, 3],
[4, 5, 6]]
Dimension of matrix : number of rows * number of columns.
E.g., The Dimension of above matrix is : 2 * 3 = 6, also called R(2*3).

Vector : An n * 1 matrix
[[13],
[14],
[5],
[87]]
R(4)
y(i) : ith element

Using 1-index vectors in Linear Algrebra review.
Using 0-index vectors in machine learning section.

Uper case for matrix, e.g. A, B, C, X
lower case for vector, e.g. a, b, c, x


1.4.2 Addition and Scalar Multiplication
To add two matrices, is to add up the elements of these matrices one at a times
E.g., 
[[1, 0],
[2, 5],
[3, 1]]
+
[[3, 0.4],
[4, 2],
[1, 4]]
=
[[4, 0.4],
[6, 7],
[4, 5]]

multiply 3 by an this matrix : take the elements of the matrix and multiply them by 3, one at a time.
3 
* 
[[1, 0]
[2, 5]
[3, 1]]
=
[[3, 0]
[6, 15]
[9, 3]]

1.4.3 
Matrix Vector Multiplication
A * x = y
(m*n matrix) * (n*1 matrix) = (m-D vector)
to get y(i), multiply A's i-th row with elements of vector x and add them up.

Code in Octave
h(x) = -40 + 0.25 x
DataMatrix : 
[2014,
1416,
1534,
852]

Prediction = DataMatrix * Paramters.
[[1, 2014],
[1, 1416],
[1, 1534],
[1, 852]
* 
[[-40]
[0.25]]

1.4.4 Matrix Matrix Multiplication
Figure out the parameters a0 and a1 all in one shot, without needing an iterative algorithm like gradient descent. It turns out that matrix-matrix multiplication is one of the key steps that you need to know

Exmaple 
![](images/1.4.4_example.png?raw=true)
(m*n matrix) * (n*o matrix) = (m*o matrix)
![](images/1.4.4_mathExpress.png?raw=true)
![](images/1.4.4_Multi-hypothesesExample.png?raw=true)

All the top ten most popular programming languages will have great linear algebra libraries.

1.4.5 Matrix Multiplication properties
Let A and B be matrices. Then in general, A * B != B * A (not commutative)
![](images/1.4.5_notCommutive.png?raw=true)

Matrix is associative
A * ( B * C ) = ( A * B ) * C

Identity Matrix
I (or I(n*n))
A * I = I * A = A
![](images/1.4.5_IdentityMatrix.png?raw=true)

1.4.6 Inverse and Transpose
If A is an m*m matrix (square matrix), and if it has an inverse
A * A(-1) = A(-1) * A = I
Nowadays, There are good numerical software for taking a matrix and computing its inverse.

Matrices that don't have an inverse are "singular" or "degenerate", e.g.,
[[0, 0]
[0, 0]]

Transpose
Let A be an m*n matrix, and let B = AT
Then B is an n*m matrix, and
B(i,j) = A(j,i)




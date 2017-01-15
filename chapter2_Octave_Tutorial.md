chapter 2 Octave Tutorial

1) Basic Operation
To prototype algorithm by Octave
To build a very large scale deployment for the prototype algorithm, re-implementing the algorithm by C++ or Java or other language

The most common prototyping language for machine learning are : 
Octave, Matlab, Python, NumPy, and R.
Python, Numpy syntax is clunkier than the Octave syntax.

start octave
>> octave --no-gui
>> ~=           % means unequals
>> disp('xxx')  % print xxx
>> ones(2:11)   
v =   2    3    4    5    6    7    8    9   10   11
>> A = ones(3, 2)
ans =
   1   1
   1   1
   1   1
>> hist(v)      % show the histogram of v
>> size(A)      % show the size of A
>> rand(47, 1)  % generate an 47 rows, 1 column matrix with the random value (0 < x < 1)
>> ones(47, 1)  % generate an 47 rows, 1 column matrix with the value 1.

2) Moving Data Around
>> A = [1 2; 3 4; 5 6]
A =
   1   2
   3   4
   5   6
>> A(3, 2)                  % access element by indexes
ans =  6
>> A( :, 2)                 % access all elements on 2nd column
ans =
   2
   4
   6

>> A([1 3], :)              % access all elements on 1 or 3 rows
ans =
   1   2
   5   6

>> A( :, 2) = [ 10, 11, 12]     % assign value to the specified elements
A =
    1   10
    3   11
    5   12
>> A = [A, [100; 101; 102]]     % append another column vector to right
A =
     1    10   100
     3    11   101
     5    12   102
>> A(:) % put all elements of A into a signle vector
ans =
     1
     3
     5
    10
    11
    12
   100
   101
   102


>> A = [1 2; 3 4; 5 6;]
A =
   1   2
   3   4
   5   6

>> B = [11 12; 13 14; 15 16]
B =
   11   12
   13   14
   15   16

>> C = [A B]
C =
    1    2   11   12
    3    4   13   14
    5    6   15   16



construct matrices 
>> A = rand(3, 1) * 1000
A =
   813.14
   589.33
   394.87

>> B = ones(3, 1)
B =
   1
   1
   1

>> C = [A B]
C =
   813.1375     1.0000
   589.3348     1.0000
   394.8678     1.0000

>> C = [A; B]
C =
   813.1375
   589.3348
   394.8678
     1.0000
     1.0000
     1.0000



3) Computing on Data
>> A = [1 2; 3 4; 5 6]
A =
   1   2
   3   4
   5   6
>> B = [ 11 12; 13 14; 15 16]
B =
   11   12
   13   14
   15   16
>> C = [1 1; 2 2]
C =
   1   1
   2   2
>> A * C
ans =
    5    5
   11   11
   17   17

% element operation
>> A .* B  % take each element of A and multipy it by the corresponding elements B
ans =
   11   24
   39   56
   75   96

>> A .^ 2
ans =
    1    4
    9   16
   25   36

>> log(A)
ans =
   0.00000   0.69315
   1.09861   1.38629
   1.60944   1.79176
>> log(2)
ans =  0.69315

>> exp(v)  % base e exponentiation of these elements
ans =
    2.7183
    7.3891
   20.0855
>> e ^ 1
ans =  2.7183
>> e ^ 2
ans =  7.3891

>> abs([ -1; 2; -3])
ans =
   1
   2
   3

>> A
A =
   1   2
   3   4
   5   6
>> A'       % the tranpose of A
ans =
   1   3   5
   2   4   6

>> a = [1 15 2 0.5]
a =
    1.00000   15.00000    2.00000    0.50000
>> max(a)
ans =  15
>> [val, ind] = max(a)
val =  15
ind =  2







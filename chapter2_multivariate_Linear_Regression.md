2.1 Multivariate Linear Regression

1) Multiple Feature
x1    x2    x3    x4    y
2014  5     1     45    460    |
1416  3     2     40    232    | m = 47                                                                   
1532  3     2     30    315    |
...   ...   ...   ...   ...    |

m = number of training example
n = number of features, here is 4.
x(i) = input(features, or the row) of i-th traning example
x(i,y) = value of feature j in i-th training example

E.g., x(2, 4) = 2

2) multiple Varariate
h(x) = a0 + a1x1 + a2x2 + ... + anxn
For convenience of notation define x0 = 1, infer to 
h(x) = a0x1 + a1x1 + ... + anxn
     = aTx
![](images/2.1.1_simple_express.png?raw=true)
![](images/2.1.2_multivariateSimpleExpress.png?raw=true)
![](images/2.1.2_MultipleGradientDescent.png?raw=true)

3) Gradient Descent in Practice 1 - feature Scaling
Idea : make sure features are on a similar scale
E.g. 
x1 = size(0-2000)
x2 = number of bedrooms (1-5)
=> 
x1 = size / 2000
x2 - number of bedrooms / 5

So that 0 <= x1 <= 1 and 0 <= x2 = <=1

Get every feature into approximately a -1 <= x <= 1.

Mean normailization
    Replace xi with xi-ui to make features have approximately zero mean (Do not aply to x0 = 1)
E.g.
x1 = (size - 1000) / 2000
x2 = (#bedrooms - 2) / 5

x1 = (x1 - u1) / s1
u1 : avarage value of x in training set
s1 : range (max - min), (or, standard deviation)
The feature scale doesn't have to be too exact.

4) Gradient descent in Practice 2 - Learning Rate
'Debuging' : Making sure gradient descent is working correctly.
    J(a) should decrese after every iterator

Example automatic : convergence test : 
Declare covergence if J(a) decreases by less than a thredhold (e.g. 0.001) in one iteration.

Chosing what this thredhold is is pretty difficult, so in order to check your gradient descent convergence, prefer to check the graph of J(a) change line.

Example : Gradient descent increase after each iterator
solution : user smaller learning rate
![](images/2.1.4_gradient_descent_increase.png?raw=true)

Summary : 
    If learning rate is too small : slow convergence
    If learning rate is too large : J(a) may not decrease on every iteration; may not converge..
![](images/2.1.4_choose_learning_rate.png?raw=true)

5) Features and Polynomial
Polynomial Regrssion Example
It's important to apply feature scaling if you're using gradient descent to get them into comparable ranges of values
![](images/2.1.5_ploynomialExample.png?raw=true)



2.2 Multivariate Linear Regression
1) Normal Equation
![](images/2.2.1_intuitionOfNormalEquation.png?raw=true)
![](images/2.2.1_exampleOfNormalEquatation_1.png?raw=true)
a = (XTX)(-1)XTy
Octave : pinv (x'*x)*x'*y

Feature Scaling is not neccessary for Normal Equation. If you are using gradient descent, feature scaling is still important.

m training examples, n features.      
  Gradient Descent                  |  Normal Equation
> Need to choose learning rate      |> No need to chose learning rate
> Needs many iteratives             |> Do not need to iterate
                                    |
> work well even when n is large    |> Need to compute (XTX)(-1)
                                    |> Slow if n is very large 
n > 1000,000 still work fine        |  (n < 1000 is fine)

Normal Equation is good at solving linear regression with not large features, but be slow when features are large and do not work for other complex learning algorithm. 
Gradient Descent work fine on other complex learning algorithm, for example classification algorithm, like logistic regression algorithm

2) Normal Equation and Noninvertibility
< Optional section >
What if XTX is non-invertible? (singular / degenerate)

Just pinv in Octave
Octave : pinv(x'*x)*x'*y
in Octave : 
    pinv : pseudo invert
    inv : invert

Cause 1, Redundant feature (Linearly dependent)
E.g.  x1 = size in feet(2)
      x2 = size in m(2)
    solution : delete the redundant feature.

Cause 2, Too many features (e.g. m<n).
    solution : Delete some features, or use regularization






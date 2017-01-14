1.1 Machine Learning Introduction

1.1.1 welcome
Machine Learning
    -   Grew out of work in AI
    -   New capability for computers

Examples : 
    - Database mining 
        Large datasets from growth of automation/web.
        E.g., Web click data, medical records, biology, engineering.
    - Applications can't program by hand
        E.g., Autonomous helicopter, handwriting recognition, most of Natural Language Processing(NLP), Computer Vision.
    - Self-customizing programs
        E.g., Amazon, Netflix product recommendations

1.1.2 Supervised Learning
Supervised Learning
    right answers is given
    in every example in our data set, we are told what is the "correct answer" that we would quite liked the algorithms have predicted on that example.

Regression 
    Predict continuous valued output(house price)

Classification
    Predict discrete valued output( 0 or 1)

1.1.3 Unsupervised Learning
Given the data set, we're not told what to with it and not told what each point is. Instead we are just told, here is a data set. Can you find come structure in the data ?

clustering, is just one type of Unsupervised Learning

If use the right programming environment, many learning algorithm can be really short programs
Octave, is an open source software. Use an tool like Octave or Matlab. Many learning algorithms become just a few lines of code to implement.
First prototype our software in Octave, because softwares in Octave makes it incredibly fast to implement these learning algorithms

Cocktail party problem algorithm
[W,s,v] = svd((repmat(sum(x.*x,1), size(x,1,1).*x)*x');


1.2.1 Model Representation
step1 : Training Set -> Learning Algorithm -> h(hypothesis)
step2 : input(x) -> h -> output(y)
h, is a function that maps from x's to y's
E.g., Size of house -> h -> Estimated price

Linear regression with one variable, or Univariate linear regression

1.2.2 Cost Function
Example : Predict the price of an house, according its size
Hypothesis : h(x) = a0 + a1x
a(i) : Parameter

J(a0, a1) = (1/2m)|i=1->m|(h(x(i)) - y(i))^2
h(x) = a0 + a1x
minimize J(a0, a1) : choose a0, a1 so that h(x) is close to y for our training example(x, y)
This cost function is also called the squared error function.

The square cost function is the probably the most commonly used one for regression problems.

1.2.3 Cost Function Intuition 1
h(a1)(x) : for fixed a1, this is a function of x.
J(a1) : function of parameter a1.
![](images/1.2.3_univariable_cost_function.jpg?raw=true)

1.2.4 Cost Function Intuition 2
h(a0, a1)(x) : for fixed a0, a1, this is a function of x.
J(a0, a1) : function of the parameters a0, a1. 
vivual software : 3-D suface 
simpler vivual express : counter plot
![](images/1.2.4_1.png?raw=true)
![](images/1.2.4_2.png?raw=true)

1.3.1 Gradient Descent
Have some function J(a0, a1)
Want  min(a0, a1) J(a0, a1)

Outline : 
    Start with dome a0, a1
    Keep changing a0, a1 to reduce J(a0, a1) until we hopefully end up at a minimum
![](images/1.3.1_1Gradient_Descent.png?raw=true)


Gradient Descent algorithm 
repeat until convergence
![](images/1.3.1_2math.png?raw=true)
':=' means assignment, is an computer operation, to set right to left
a := b
a := a + 1 

'=' means truth assertion
a = b

1.3.2 Gradient Descent Intituition
ai := ai - a(c/c ai)J(a0, a1) (for i = 1 and i = 0)

a : learning rate
(c/caj)J(a0, a1) : devirative

converge with one parameter a0, j(a0)
![](images/1.3.2_converge.png?raw=true)

If a is too small, gradient descent can be slow
If a is too large, gradient descent can overshoot the minimun, It may fail to converge, or ever diverge.

If your parameter are already at a local minimum one step with gradient descent does obsolutely nothing it doesn't change your parameter, which is what you want because it keeps your solution at the local optimum

Gradient descent can converge to a local minimum, even with the learning rate a fixed. As we approach a local minimum, gradient descent will automatically take smaller steps, So no need to decrease a over time.
![](images/1.3.2_3_auto_smaller_setps.png?raw=true)


1.3.3 Gradient Descent for Linear Regression.
One of the issues with gradient descent is that it can be susceptible to local optima

The cost functio for linear regression is alwasys going to be a bow shaped function, called Convex function.
Convex function means a bowl shaped function, so this function doesn't have any local optima except for the one global optimum


Does gradient descent on a bow shaped function (convex function) whenever you are using linear regression, it will always converge to the global optimum. Because there are no other local optimum, global optimum
![](images/1.3.3_Gradient_descent_on_square_error_cost_function.png?raw=true)

"Batch" Gradient Descent
"Batch" : Each step of gradient descent uses all the training examples.

There exists a solution for numerically solving for the minimum of the cost function J without needing to use an iterative algorithm like gradient descent. These method is called the normal equations mehtonds.
But that gradient descent will scale better to larger datasets than normal equation mehtonds.





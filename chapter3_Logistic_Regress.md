### 3.1.2 Hypothesis Representation###

Linear regression hypothesis
ha(x) = aTx

Logistic Regression Mode
Ha(x) = g(aTx)
g(z) = 1 / (1 + e^(-z))     %sigmoid function or logistic function.

ha(x) = 1 / (1 + e^(-aTx))



![](images/3.1.2_1Logistic_Regression_Model.png?raw=true)

Interpretation of Hypothesis Output
ha(x) = estimated probability that y = 1 on input x.
ha(x) = p(y = 1 | x; a)

### 3.1.3 Decision Boundary###

ha(x) = g(aTx)
g(z) = 1 / (1 + e^(-z)),   Suppose 

predict "y=1" if ha(x) >= 0.5  

​                              aTx >= 0

predict "y=0" if ha(x) < 0.5

​			       aTx < 0				

​		

![](images/3.1.2_2Logistic_Regression_explain.png?raw=true)



# 3.2 - Logistic Regression Mode#

### 3.2.1 - Cost Function###

Cost Function
Linear regression : J(a) = 1/m....
Cost(h(x), y) = 1/2....

Because the very nonlinear function that appears in the middle of Cost Function, J of the theta ends up being a nonconvex function if you were to define it as a square cost function. 

What we do is to come up with an different function, that is convex
Logistic regression cost function

Cost(h(x), y) =       -log(h(x)), if y = 1

​                          -log(1 - h(x)), if y = 0

![](images/3.2_1_1_logistic_regression_cost_function_yEqual1.png?raw=true)



![](images/3.2_1_2_logistic_regression_cost_function_yEqual0.png?raw=true)




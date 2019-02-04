# Introduction

#### What is Pattern Recognition?

It is the field that concerned with the **automatic discovery** of regularities in data using computer algorithms and use this regularities to take actions such as classifying the data into different categories.

Ways for the automatic discovery for the regularities:

* Handcrafted rules.
* Heuristics
* Machine Learning
* ... etc

### Machine Learning:

* Is approach in which a large set of N digits {x1 , . . . , xN } called a training set is used to tune the
  parameters of an adaptive model. 
* The goal of the machine learning is to generalize over unseen data.
* For most practical applications, the inputs are  preprocessed and transformed to another new space to:
  * To help the machine algorithms in solving the problem.
  * To speed up the computation

But the most important thing that: **Preprocessing should preserve the discriminatory information** that enabling to take the right decision.

i.e if the goal is real-time face detection in a high-resolution video stream,the computer must handle huge numbers of pixels per second, and presenting these directly to a complex pattern recognition algorithm may be computationally infeasible. 

**Problems in Machine learning can be classified to**:

##### 1) Supervised learning:

Here is, the training data comprises the inputs vectors along with corresponding outputs vectors.

It is divided to **Classification** problems and **Regression **problems.

##### 2) Unsupervised learning:

Here is, the training data comprises the inputs vectors without corresponding outputs vectors.

it comprises:

* Visualization, project data from high dimension space to low dimension space.
* Clustering, discover groups of similar examples in the input space.
* Density estimation, determine the distribution of data of in input space.
* ...

##### 3) Reinforcement learning:

Here is, the goal is to find suitable actions in given situations ( states) to maximize a reward.

##### 

There are **three** important tools needed to understand and apply machine learning efficiently:

1. **Probability theory**, a framework to express and quantify the uncertainty in a precise way.  

2. **Decision theory**, how to use the probability model to take optimal decisions.

3. **Information theory.**



## 1) Probability Theory:

* If  **X **and  **Y** are random variables:

  * **Discrete**

  * $$
    P(X)=\sum_y{}P(X,Y)---\text{Sum Rule}\\ 
    P(X,Y)=P(X|Y)P(Y)--- \text{Product Rule}\\
    $$

  * **Continuous**

$$
P(X)=\int_ y P(X,Y)---\text{Sum Rule}\\ 
P(X,Y)=P(X|Y)P(Y)--- \text{Product Rule}\\
$$

* **Bayes's Theorem**

$$
P(X=x|Y=y)=\frac{P(Y=y|X=x)P(X=x)}{P(Y=y)}
$$



* **Expectation**

  * **Discrete**
    $$
    E[f]=\sum_x{P(X=x)f(X=x)}
    $$

  * **Continuous**:

  * **Intuition**:
  In layman's terms, an Expectation is the sum of all the probabilities occurring multiplied by their respective values, which ends up equating to the system's arithmetic mean.

  If we were to take the example of a 6-sided die roll, calculating the expected value would work as follows:
    Expected Value for Y = SumForAllValuesOfY((value of Y) * (probability of Y occuring))
    Hence E = 1(1/6) + 2(2/6) + 3(3/6) + 4(4/6) = 5(5/6) + 6(6/6) = 3.5

  What this means is that if we had enough time and patience to roll a dice for all eternity, add up the values of all the dice rolls, and divide it by the number of times we threw the dice, 
  it would yield 3.5 (the average value across all throws).

  Thus the expectation of a system is the system's mean.

  Sidenote: It is worth noting that in the case of a system with continuous variables, one has to integrate over the possible values, instead of summing over them.

  

$$
E[f]=\int_x{P(X=x)f(X=x)}
$$

* In case of  **E(X,Y)** , X,Y are discrete
  $$
  \begin{align*}
  E_x[f(X,Y)]&=\sum_x{f(X=x,Y=y)P(X=x)}\\
  &= f(Y) =\text{will be a function in y}.
  \end{align*}
  $$


* In case of E(X|y) , X,Y are discrete
  $$
  E_x[X|Y]=\sum_x{f(X=x)P(X=x|Y=y)}
  $$


* **Variance**
  $$
  \begin{align*}
  Var(f(X=x)) &=E[ (f(X=x)-E[X=x])^2 ]\\
  &=E[f(X=x)^2]-E[X=x]^2
  \end{align*}
  $$

  * **Intuition**:
    The variance of a system shows how "spread out" a system is, and can be thought of as the average distance from the system's expected value. The higher a system's variance, the more spread out it's values are,
    and the further it strays from the expected value. Square rooting the variance of a system yields the system's standard deviation.

* **Covariance**
  $$
  \begin{align*}
  Cov(X,Y)&=E_{x,y} [ (X-E[X] ) (Y-E[Y])]\\
  &=E_{x,y}[XY]-E[X]E[Y]
  \end{align*}
  $$
  If X,Y are vector of random variables:
  $$
  \begin{align*}
  Cov(X,Y)&=E_{x,y} [ (X-E[Y^T] ) (Y-E[Y^T])]\\
  &=E_{x,y}[XY^T]-E[X]E[Y^T]
  \end{align*}
  $$

  * **Intuition**:
  Covariance is a measure of how much two random variables vary together. It’s similar to variance, but where variance tells you how a single variable varies, covariance tells you how two variables vary together.
  Scaling their covariance by the product of their standard deviations yields their correlation coeefficient, which can be thought of as a measure of the strength of the relationship between the two variables.




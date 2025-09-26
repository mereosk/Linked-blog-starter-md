
2025-09-15 11:57

Status:

Tags:

# MAIR Lecture 4

## Advanced Machine Learning

In page 25 

- **Precision** = out of all predicted positives, how many are truly positive?
    
- **Recall** = out of all actual positives, how many did we correctly predict as positive?

If the threshold goes up means that we will have more TP so precision goes up.
If the threshold goes up means that we have lost a lot of positives between 0.5 - 0.8, so we will have a lot of FN 

### Linear and non-linear
### 🔹 Fast Intuition

- If the decision boundary is a single straight line (or hyperplane in higher dimensions) → linear.
    
- If the boundary can bend, curve, or form irregular shapes → non-linear.
## Logistic regression

To reach logistic regression we have to start with **linear regression**

We want to minimise the loss function for optimization.

> y^ is the predicted value.

Why do we need 1/2 we will have to differentiate so the 2 will come in front.

For the classification task we want a **discrete** output. We can transform it to a probability in the range 0 to 1 using the **sigmoid** function or logistic function.
![[Pasted image 20250915153430.png]]

Sigmoid: squases the value into 0 and 1

page 22: Why do we take the log? 

> Sigmoid has some nice derivatives, which we want.

We **dont** want sign function since it is not differentiable. 

Is the **decision boundary** is linear or not? 
This is still a linear classification since Logistic regression is a linear classifier. And also decision trees  and nearest-neighbor are NOT linear classifiers

**Linear data** are the data that can be perfectly split by a straight line.

## Loss function

We want y^ to be as close as possible to y. We want to maximise this
![[Pasted image 20250915155141.png]]
When y = 0 we are with 1-y^ to maximize

We dont like working with exponents so we log

How can we turn this into minimization problem? We flip the sign.

### Cross entropy loss

![[Pasted image 20250915155415.png]]

### Gradient descent

![[Pasted image 20250915161723.png]]
The generalization of this is
![[Pasted image 20250915162229.png]]

In the page 57 calculate each loss for each parameter. An alternative would be to calculate it for everything but it is computational difficult, so we are using batch sizes.

### Regularization

Avoiding overfitting.. thsi can be done with regularization. We are adding λR(θ), penalize high level complexities. We want to have a low loss but also as low as a complexity as possible. 

How to calculate model complexity??? 
> By using L1 and L2 norms

### L2 regularization (or, ridge regularization)

![[Pasted image 20250915163458.png]]
We also have a λ, which is a value that tells us how much we should regularize.
Shrinks the values close to 0 but doesn't go to 0 anymore.
### L1 regularization (or, lasso regularization)
![[Pasted image 20250915163556.png]]
It will force some feature to go to 0.

### How can we extend this

Binary classification (0 vs 1)
**Multiclass** classification

One hot encoding
then use **softmax**

## Neural networks

Building block of neural nets
![[Pasted image 20250915164708.png]]

After that we could use an activation function, and preferably it should be non-linear. We could use **sigmoid** again. What about the hidden layers? Usually we use tanh
![[Pasted image 20250915164932.png]]

But the most simple and better is ReLU which is very very simple and behaves very nice.
![[Pasted image 20250915165016.png]]

A neural network with a lot of hidden layers that use linear activation function is STILL a linear model.

XOR check it out yourself

NN have **forward and backward propagation**




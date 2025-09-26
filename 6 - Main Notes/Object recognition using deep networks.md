## Lab assignment 1 - Challenge-based exercise


2025-09-26 09:14

Status:

Tags:

# Object recognition using deep networks


### Question 1

>Research and describe the principles of overfitting. Describe how AND WHY dropout can reduce this, citing your sources. 

**Overfitting** is a general problem in supervised machine learning as well as in data science.  The problem is that the network does not generalize well on test data, when it does well on observed or training data. This can be due to several reasons, for example:
1. The model **learns noise** very well so it cannot generalize.  This can happen when there is too much noise or  the training set is too small in size.
2. If a model is too complex (has too many parameters or considers too many inputs), it may fit the training data very accurately, but its predictions can vary a lot when applied to new datasets. This is called **complexity of a hypothesis**
3. We use multiple comparison procedures, where we select the maximum score from an evaluation function. However, this score may inhibit the classification accuracy. For example in a spam detector,  some rare words may be correlated with spam, but if the procedure chooses them, they will not generalize well in test data.

Thus the problem of overfitting has bothered scientists a lot and there are many solutions proposed in order to tackle it. However, we shall focus on **dropout**. The idea is that net network will drop units randomly during the training procedure, which will avert units from co-adapting. The procedure of dropout is:
1. Make a simpler network by randomly dropping an amount of units.
2. Continue the training using **Stochastic Gradient Descent**. (For neurons that were dropped, their gradient is set to zero)
3. Restore the units that were removed.
4. Again, remove a random amount of neurons.
5. Continue this process until the network converges (learns good parameters).
All in all, **dropout prevents overfitting** by making the network less dependent on specific neurons, forcing it to learn general patterns, thus not memorializing data.

References
- https://elitedatascience.com/overfitting-in-machine-learning
- Paris G., Robilliard D., Fonlupt C. (2004) Exploring Overfitting in Genetic Programming. Artificial Evolution, International Conference, Evolution Artificielle, Ea 2003, Marseilles, France, October. DBLP, pp.267-277.
- Srivastava N, Hinton G, Krizhevsky A, et al. (2014) Dropout: a simple way to prevent neural networks from overfitting. Journal of Machine Learning Research, 15(1):1929-1958.
- https://en.wikipedia.org/wiki/Overfitting
- Ying, X. (2019). An Overview of Overfitting and its Solutions. _Journal of Physics Conference Series_, _1168_, 022022. https://doi.org/10.1088/1742-6596/1168/2/022022

### Question 2

>Plot the training history (as in Learning-based Exercise One). Include this in your answer document.

![[Pasted image 20250926101728.png]]

### Question 3

> How much longer does it take to run each training epoch for this model, compared to the most similar convolutional model for digit recognition (Learning-based Exercise One, Question 7?) (This should be clear, even in Google Colab).

| Current model's time                 | CNN's time for digit recognition     |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20250926101843.png]] | ![[Pasted image 20250926102005.png]] |
As we can see, each training epoch in this model takes almost twice as long as in the CNN used for digit recognition in Learning-Based Exercise 1.

### Question 4

> Give at least two factors that may contribute to this difference, explaining each.

| ![[Assets/model.png]]        | ![[Assets/model_cnn_1st.png]]       |
| ---------------------------- | ----------------------------------- |
| Model for object recognition | Model for mnist numbers recognition |

The models image will help us understand the reasons that contribute to the time difference between the two CNN models.

- **Smaller batch size:** more weight updates → per-epoch time increases (~3–4× if batch size dropped from 124 → 32).

- **Larger network:** extra conv layers + bigger dense layer → per-epoch computations increase, possibly 2× slower.

- **RMSprop with small learning rate:** may require careful convergence → effectively slower.





## Reference

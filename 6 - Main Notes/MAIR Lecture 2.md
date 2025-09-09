
2025-09-09 23:18

Status: #1/10

Tags: [[Artificial_intelligence]] [[Decision_trees]] [[Methods_in_ai_research]] [[University]]

# MAIR Lecture 2


## Experience
1. Supervised learning
2. Unsupervised learning
3. Reinforcement learning

## Supervised Learning
> We have labeled data eg. spam not spam

![[Pasted image 20250908153520.png]]

**Hypothesis space** : this is very important
Learning algorithm: Defins a **data-driven** search over the hypothesis space.

1. **Regression**, the y is a real number in space. We will be able to provide a predection. 
2. **Classification**: if the target is a category. Lets say Breast cancer diagnosis(malignant or benign). For example the radius of the mass.
3. **another one** ??
### Learning

Generalization $\neq$ Memorization

### Decision Trees
![[Pasted image 20250908154605.png]]
Can be represented by *if* *else* rules

**Information Gain**
Expected reduction in entropy due to sorting on A.
Intuitively: Degree of disorder or randomness
![[Pasted image 20250908155710.png]]
IMPORTANT formula!!

We choose outlook as a rout because it has the maximum information or something

### Decision boundary

Page 71.
U can see that the tree tries too hard, overfitting

### Inductive bias
What type of solutions are we more likely to prefer ?? 

### When to consider Decision Trees

-  Instances describable by attribute – value pairs
-  Target function is discrete valued
-  Disjunctive hypothesis may be required
-  Possibly noisy training data

### Model selection
**Performance metrics**
1. Accuracy -> Confusion Matrix.
2. Precision
3. Recall

|             | Truth A | Truth B |
| ----------- | :-----: | :-----: |
| Predicted A |   70    |   40    |
| Predicted B |   30    |   60    |
 Dont do a selection on model from the **training set**

### Train & dev & test data
![[Pasted image 20250908164144.png]]
### Cross validation
Another option
![[Pasted image 20250908164201.png]]

### Overfitting and Underfitting

**Underfitting**: Your model is a bit too simple, it didn't learn enough.
**Overfitting**: Your model has memorized too much. The model doesn't generalizes well
![[Pasted image 20250908164453.png]]
>The longer the right we are the **deeper** we are in decision trees
>The yellow is the boundary between overfitting and underfitting

### Evaluation metrics

Answer: a classifier that only predicts 1 would make an accuracy of **70%**
As we said accuracy, precision and recall

*QUESTION* 1: How can we compute the confidence of a decision tree?
*QUESTION* 2: Come up with a task for which precision is more important, and a task for which recall is more important


## Unsupervised Learning

> Unlabeled data, community detection

## Reinforcement Learning

This is a bit different that the previous 2.

## Reference
[[MAIR Lecture 2]]

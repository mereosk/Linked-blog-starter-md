
2025-09-10 12:12

Status: #1/10

Tags: [[ML for Human Vision and Language Lecture 1]] [[Artificial_intelligence]] [[University]]  [[Machine_learning]]

# ML for Human Vision and Language

> The main conceptual inspiration for **deep learning is the brain**

## What is a deep netwrork?
- A learning network that **transforms** or **extracts** features using:
	- Multiple nonlinear processing units
	- Arranged in multiple **layers** with
		- **Hierarchical organisation**
		- Different levels of **representation** and abstraction. About representation, at the input layer the representation is raw data like pictures. Afterwards, the network transforms it into new representation, thus the network leans to highlight the most useful aspects of the input for solving the task.

## What is machine learning

>A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P if its performance at tasks in T, as measured by P, improves with experience E.’ (Tom Mitchell, 1998)

## Inside layers

![[Pasted image 20250910123656.png]]
- **Filter & Normalization** are **linear**
- **Threshold & Pooling** are non linear but the later is optional

### Filter/Convolve operation

- A large set of filters are used in parallel to produce multiple maps of where their filter patterns are seen, ofter called **feature maps**
![[Pasted image 20250910134137.png]]

### Threshold/Rectification operation

- Nonlinearity is introduced here.
- The goal is to activate the output feature map if its values reaches a certain level

Most common is **ReLU** or **Rectified linear unit** $f(x) = max(0,x)$
![[Pasted image 20250910135220.png]]

### Pooling operation

> Neighbouring units are representing very similar information so pooling operation **downsamples** the units to improve computational efficiency

**Pooling** operation discards some data in favour of computational efficiency
1. By discarding details, pooling forces the tework to focus on stronger and more general features, thus **reduces overfitting**
2. 

## Reference

[[Lecture 1_Deep learning in artificial networks.pdf]]

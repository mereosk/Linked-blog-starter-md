
2025-09-10 15:16

Status: #5/10

Tags: [[Machine_learning_for_human_vision_and_language]] [[Deep_learning]] [[University]]

# Ml for Human Vision Language Lecture 2

![[Pasted image 20250910151938.png]]

The strength of synaptic connections are the biological equivalent of the **weights** in a filter kernel in artificial neural network.

A **protein** like **ion channel** can change **shape**. 

> SODIUM = Νάτριο
> Potassium = Κάλιο

> The third protein is an active mechanism, in needs energy to do its job.

Glutamate and GABA are the most well known ... 

### Opening the ion chanel
If there is a change in membrane, the positive one goes to the outside the soduous come on and changes the voltage

Outer segment closes the ion

> The process is a loop also it is like a electrical transistor (like XOR gate)

When we reach the activation threshhold then the ion gates open and the neurons is spiking due to large electrical activity. There is lot of sodium pass in
![[Pasted image 20250910153531.png]]
Like relu, when we reach a threshold (relu  is 0 ) then it is spiking. 0 doesnt mean anything in biology, thus the different threshold.

Biological neuron can reach a maximum activation. Important if we try to simulate em

### Activation of neuron
![[Pasted image 20250910154020.png]]

page 12

The GABA pushes CL- so it makes it more negative.

page 13

the blue is GABA thus the negative. It makes the possynaptic neuron less likely to fire. U can see it from the graphs

page 14

EPSPs should be the most in order to neuron to fire.

THAT is what we simulating with a filter.

### Neurotransmiter release

When action potential arrives it activates voltage gated calsium channel. The bubbles are held by a web of protein. The calsium changes their shapes. 

![[Pasted image 20250910160633.png]]
After pooling there is a stach with feature maps

Fully Connected is the output layer
![[Pasted image 20250910161020.png]]

We want to connect the score with a probability. That we can do with **softmax activation function** 

The probabilities have to add up to 1

> In machine learning the goal is to find the optimum **convolution filter**

### Feedforward processing

$fk = td*xd + tk*xk + t1*x1$ 
All of these is a big horribly set of equations

![[Pasted image 20250910161606.png]]

page 24 
We are trying to **minimize** the **RMS** <-- Cost function

## Grαdient descent
![[Pasted image 20250910162331.png]]

> Derivatives can be linked together. **Chain Rule**

### Weights in biological neurons
Backpropagration of error is mathematically proven the best.

page 32
	Supervised process we tell to animal what to do.
	

> Cells that fire together, wire together ~Hebbian learning

### Color map comparison filters

A color is red if the red filter is activated and green is NOT activated. Similarly, in yellow if red and green are activated and blue is not activated.
That is the first feature comparison we are doing. We nextly do **spatial comparison**. The bipolar will response to changes of light. Changes from lightness to changing of lightness or **CONTRAST**.

The normalization is different than before, this looks at a specific area. Whereas, the other looked at the whole.

## Reference

[[Lecture 2_Deep learning in biological networks.pdf]]
[[Action Potential in the Neuron]]
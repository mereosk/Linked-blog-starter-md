
2025-09-24 15:16

Status:

Tags:

# ML for Human Vision Language Lecture 4

page 3
recurrency mens that the activity goes back to itself
page 4
Neurons in an area also are affected by neurons around them and not only the input.  The local inhibition is like doing from + to -. One neurons activity affects another where the other affects the first one (RECURRENCY).

cONVOlutional recurrency, a neuron is affected only by neighbors and not from everything.

page 6

Voltage at an electron goes up and down, we also see a lot of neurons firint and when the wave is low not much spiking activity is happening.

page 7

we hve an input x and and output o and the state of the hidden layer h will affect its own state in the future. After that there is 3 timesteps xt-1 comes in the activity changes and that pas state of hidden area as well as the xt affects the activity in the hidden layer ht. This is very important in text-to-speech synthesis, so that we sound natural and speech recognition adn language semantic comprehension as well as language translation. 

Fully connected interaction

page 8

BTT bottom up lateral and top-down. We have seen the first one(feehe readout will get us the answer that we want.

page 10

Can this be made? The have new abilities. 

page 11

When we have light debris almost all do well

The second and second set of bars we use more filters. BF is larger filters and BK has more filters. The other 3 have extra connections. 

page 13

This is a 2 laer network. the recurrent network these leyers have the same filters but layers are doing more operations.  All those transformations make the network deeper, thus compromises must be done.

page 14

the red is a 4 layer NN and is doing as good as 169 feed forward NN. Brain score the ability of NN to follow the brain activities. Ability to recognise things.

page 15

densenet are NN they have skip connections the higher layers can take connections from layers way bolow. So cornet_s does something special.

page 16

Lateral connections. All of the unist are connected to each others bidirectionlely. 

All the T units activated together build stronger relashionspips. When the new input come and activate only 2 units from T, then the other units will become active due to strong connections.

page 21

umans are really good in pattern recognition. FF networks are not really good at it.  But RNN (Hopfield) is doing way better than the others.

page 25

Feedback connections. Prediction of the input. I think 'i undrestand this so u can ignore that'.  Its like backpropagetion of error, the distinction is that (i dint' undrestand).

page 26

complex network layer. Input poll conv stuff then comparisson unit where the output is compared to prediction then feedforward but also goes to fully connected recurrent process, where it finds the nearest pattern, the output to prediction then loop again. 

**Self Supervised**

Predictive coding and energy efficiency

mnist numbers increasing in every frame. 1 after 2 after 3 but actually they are not alike. Minimise the activation of the units. or minimise the preactivation Why? try to minimise brain use. If we inhibited the average image (the grey line). The  bottom is average of a 3 and inhibit that.
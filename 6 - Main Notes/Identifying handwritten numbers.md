## Lab assignment 1 - Exercise 1
2025-09-06 17:46

Status: #10/10

Tags: [[Machine_learning_for_human_vision_and_language]] [[Mnist]] [[Artificial_intelligence]]


- Sodjamts Enkhbat 1860666
- Ali Ostowar 4726235
- Yifan Zhou 8259909
- -Konstantinos Mereos  7917155

# Identifying handwritten numbers

### Where is it used?
- Mobile Banking
- Automated teller machines
- Digit
for tasks like check depositing. So what is **check depositing**. A "paper check" is a financial instrument for authorizing a bank to transfer funds from the payer's account to payee's account. So an AI identifier's main targets would be:
1. date
2. payee
3. amounts (both forms)
4. signature
5. routing/account numbers (but most of the type they are not handwritten)
![[Pasted image 20250906190204.png]]
Figure 1 - Handwritten check
## Question 1

> Discuss with your group, write, then describe to your teacher, a list of at least 3   applications where **automatic recognition of hand-written numbers** would be useful.

1. I would be really useful if used in **hand-written checks**, which contain *date*, the *name of payee* , *amounts(both forms)*, *signature* that are all hard-written.
2. It would **digitize history.** Find *trends* in economic data that are always hard-written. Furthermore, it would make historic data more accessible for scientists, such as dates, census books, or tax rolls from the past.
3. Last but not least, it is very important in **postal services**, since their scanners need to process millions of ZIP codes and street numbers and sort them *instantly* and *correctly*.

## Loss and accuracy

| Loss  | Accuracy | Meaning                                   |
| ----- | -------- | ----------------------------------------- |
| Large | Small    | Huge errors on a lot of data (worst case) |
| Small | Small    | Small errors on a lot of data             |
| Small | Large    | Small errors on a few data (best case)    |
| Large | Large    | Huge errors on a few data                 |


## Question 2

> Discuss with your group, write, then describe to your teacher, how the accuracy and loss evaluated on the training and validation sets progress differently across epochs. Note the details. What does this tell us about the generalisation of the model?

![[Pasted image 20250907182620.png]]
Figure 2 - Training and validation graphs of Multi-layer perception MLP

- As we can see from the first graph the **training loss** decreases steadily from 0.40 in the first epoch, reaching its lowest point just above 0.26 in the last epoch. On the other hand, the **validation loss** starts from a lower point than that of its counterpart and with some fluctuations, reaches its minimum on the 9 epoch, after that it increases slightly and remains relative steady.  That is a very small sign of overfitting.

- Looking at the second graph, we observe the opposite trend, as expected, namely the training accuracy starts at 0.883 on the first epoch and it gradually increases to 0.926 . The **validation accuracy** begins from 0.903 and fluctuates slightly, eventually converging to roughly the same value as the training accuracy. The only point is that at 6th epoch validation accuracy value has a lower value than the training one. That is normal due to the random selection of validation data.

-  Changing the batch size and epoch hyperparameters did not appear to change the accuracy of the model much, indicating that for us to see accuracy improvements, we need to consider other ways of tuning the model.

- The largest accuracy gain is between epoch 0 and 1, which makes sense since the model adjusts weights from initial random weights.

- **Overall, this behavior indicates that the model is generalizing well**: the training and validation performance are very similar, showing that the network has learned patterns from the training data that also apply effectively to unseen data. The small differences in loss and occasional fluctuations in validation accuracy are expected and are typical for this type of model.

## Question 3

>Discuss with your group, write, then describe to your teacher, whether you think this accuracy is sufficient for some uses of automatic hand-written digit classification you gave in Question 1. Why do you think this, considering how this digit classification would work in practice? 

For **hand written checks** as well as **zip codes and house numbers** we believe that a 92% efficiency is insufficient. Even, a small error in the amount of a check could be catastrophic. Similarly, in postal services, if a zip code's letter is misinterpreted by the network, mail may not reach its intended destination. However, all of these could be mitigated by error detectors or human verification.

On the other hand, digitizing historical data is not a critical tasks, thus we believe that 92% is generally sufficient for this purpose

> **A model generalizes well when it performs similarly on training and unseen data.**

## Question 4

>  Discuss with your group, write, then describe to your teacher, how linear activation of units limits the possible computations this model can perform.

// Linear activation limits the model due to the simplicity of linear computations that are unable // to catch complex non-linear characteristics such as curves and loops in the numbers.

- By default, linear activation is unable to capture the complexities of most tasks because it only allows for linear decision boundaries. 
- Even if we stack multiple linear layers on top of each other, this ends up reducing to a single linear transformation, essentially unable to learn non-linear relationships. 
- Therefore, the model is only good at representing linearly separable functions. To truly be able to generalize well on unseen data, the neural network needs at least one hidden layer with non-linear activation.
- ReLU allows the model to learn non-linearity from the dataset making it more resistance to correlation within the data.

## Question 5

> Discuss with your group, write, then describe to your teacher, how this training history differs from the previous model, for the training and validation sets. Note the details. Explain what this tells us about the generalisation of the model.

![[Pasted image 20250907182620.png]]
![[Pasted image 20250907200500.png]]
Figure 3 - Training and validation graphs without Relu (upper 2) & with Relu

 ![[Pasted image 20250907202454.png]] ![[Pasted image 20250907202610.png]] 
Figure 4 - Running times - On the left without Relu and on the right with Relu

Lets highlight the key differences:
1. The running times (Figure 4) show that they behave similarly time-wise with Relu having a small edge. That is because the later is defined as $f(x) = \max(0, x)$ , thus being very straight forward.
2. From **Image 3**, we can see that all four metrics start from a “better” value with Relu. For example, **training loss** begins at 0.34 with Relu, compared to 0.40 without it.
3. We can also observe that all metrics are much better with ReLU. **Training loss** and **validation loss** reach approximately 0.10 and 0.1 correspondingly, while **training accuracy** and **validation accuracy** reach 0.996 and 0.976, respectively.
4. Another thing is that the validation in bot graphs has little to non fluctuation, which means that the model is **stable and consistent** on unseen data.
5. The validation metrics converge much faster, reaching near their final values by the **3rd epoch**.After that, they change very little, showing the model’s has started to overfit.

## Question 6

> Quantify the model’s accuracy and loss as before. Discuss with your group, write, then describe to your teacher, whether you think this is sufficient for the uses of automatic hand-written digit classification you listed in Question 1, and why

-  The CNN achieves **~99.7% training accuracy**,  **~98.3% validation accuracy** and **~98.7 test  accuracy**, with very low loss values. 
- 👎For the **checks** lets take 1000 sample amounts, even 13 of them being wrong there is a huge problem, thus I firmly believe that without a human supervisor or an extremely advanced error prevention system, the network shouldn't be used.
- ✔️ As for the **historical data,** I already gave the pass to the previous model with 92% accuracy.
- ✔️ **Postal codes and house numbers:** Accuracy is sufficient for reliable automatic sorting, with **error-correcting systems** catching rare mistakes.

## Question 7

> In comparison to the previous (convolutional) model: 
> 1. How does the time taken for each training epoch differ? (Google Colab may not show this clearly, in which case run this on your own hardware) 
> 2.  How does the training history differ for both the training and validation sets? 
> 3. How well does the resulting model generalise?

![[Pasted image 20250908014127.png]]
![[Pasted image 20250908012819.png]]
Figure 5 - Running times - Upper CNN without dropout and lower 
![[Pasted image 20250908010347.png]]
![[Pasted image 20250908012343.png]]
Figure 6 - Training and validation graphs CNN without dropout(upper 2) & with dropout

1. To answer the first question, we trained the model it google colab but used the CPU instead of some GPU. As we can clearly see in the figure 5 all the times of each epoch were faster without the dropout, except that of the 5th epoch. That could be due to the fact that by using dropout there are fewer neurons, since the network drops some randomly
2. From the graphs, we can observe that the **training curves are very similar**, with the main difference being that the CNN **without dropout** reaches higher accuracy and lower loss. This shows that using dropout **sacrifices some training accuracy**. However, the **validation curves converge to better values**, and they are consistently higher than the training metrics, indicating that the model **generalizes better**.
3. Overall, the dropout model **generalized much better**. By artificially introducing randomness, dropout forced the network to learn more robust patterns instead of **memorizing** training examples. The result was a model that sacrificed a little training accuracy but achieved higher and more stable validation performance. As a result, this model that not only achieves a **99%** test accuracy but also never sees its training accuracy exceed that of validation or test sets is arguably the best model at generalizing to unseen data.
## Reference

[[Lab-1-ml-for-human-vision.pdf]]

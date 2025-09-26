
2025-09-11 10:59

Status: 

Tags: [[Methods_in_ai_research]] [[University]] [[Artificial_intelligence]] [[Natural_language_processing]]

# MAIR Lecture 3

> How do we split the dataset in train/dev/test?

- <10000 70% train dev and 30% test
- If u have a huge dataset even 1% test may be enough

![[Pasted image 20250911111151.png]]

**One Hot Encoding**
- We take a vector we want to encode, and for every dimension we have either a 0 or 1
![[Pasted image 20250911111642.png]]
### Nearest neighbor

>Idea: Classify new examples based on the most similar training examples

**Four components:**
- A distance metric
- How many neighbors to look at?
- A weighting function (option)
- How to fit with the local points?

To tuckle the noise, we should **generalize**

### Choosing K
K = 1 
Sensitive
Could lead to overfitting

K = N (number of instances)
Underfitting
Dummy majority label

How can we find the best balance? 

### Distance measure

- Scaler number |3-5| = 2 in one dimension
- Euclidean distance or L2 ![[Pasted image 20250911113709.png]]
- Manhattan distance or L1![[Pasted image 20250911113719.png]]
- Minkowski distance (generalization of the previous 2)
- ![[Pasted image 20250911113836.png]]
> The default one is the **Euclidean distance**

For the problem of feature scaling we can **normalize**
![[Pasted image 20250911114210.png]]

### Decision Trees vs Nearest neighbors
Learn a model from the training data | Just store data
Selects a subset of features based on the info criteria it will choose the most important features | All featrues have equal weight -> Sensititvity to irrelevant features
Decision boundaries are axis-aligned cuts | Decision boundaries can be complex (voronoi cells)

## Natural Language Processing

What makes language understanding hard?
- Polysemy: Multiple meanings in words - Words can have multiple meanings. Difficult to contextrualize
- Syntactive ambiguity
- A lot of variation like ikr, smh etc..
### Tokenization
Chopping up sentences into words 
**Types** are the unique appearances
### Pre-processing steps
1. Stop word removal (a, the)
2. Lemmatization: sand, sung -> sing
3. Stemming (strip endings of the word)
4. Lowercasing
5. Removing infrequent words

### Edit distance
Levenshtein distance uses deletion, substitution and insertion. (type error)

### Bag of words representation
Only  look at the presence or frequency of words, ie ignore the order

> Jaccard similarity: the main idea is to look at the common tokens and divide em with the union.
> BUT, frequency and order of words are ignored

How to address it? 
A: With **vectors**

![[Pasted image 20250911122632.png]]
The two similarity in 81 doesn't agree. How to solve the problem with the euclidean distance?
### Cosine similarity
![[Pasted image 20250911123222.png]]
Cosine ranges from -1 to 1
- -1 vectors pointing in opposite directions
- 0 orthogonal
- 1 same direction

> Euclidean distance gives you the distance -> the smaller the closer they are. Cosine similarity give you a number that the bigger the closer the vectors are.

How can we encode words in the vector space? 
- With One hot encoding the **limitations** are that we have so many dimensions also we don't capture the relationship between words.

What can we do? 
![[Pasted image 20250911124217.png]]

A **better way** are **word embeddings** (Dense word vectors)
- Skipgram model

![[Pasted image 20250911124610.png]]
## Reference

[[MAIR Lecture 3]]
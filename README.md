# CS224n-NLP-with-DL
Assignment for CS224n, winter, 2019.
## Lecture 01
### How to represent the meaning of a word
For example: glasses
1. demotational semantics: refers to a specific pair of glasses
2. distributional meaning*: "glasses" defined by context
3. localist representation: a representation of a place stored, for instance, one-hot vectors
### Word2vec
In the first lecture, it mainly discusses the Word2vec method. It will firstly define the likelihood function with the parameter $\theta$, which is the vector representation of the words, and the hyperparameter $m$:
$$
L(\theta)=\prod_{t=1}^T\prod_{-m \leq j \leq m \\ j \\neq 0} P（w_{t+j} | w_t; \theta)
$$

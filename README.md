# CS224n-NLP-with-DL
Assignment for CS224n, winter, 2019.
## Lecture 01
### How to represent the meaning of a word
For example glasses:
1. denotational semantics: refers to a specific pair of glasses
2. distributional meaning*: "glasses" defined by context
3. localist representation: a representation of a place stored, for instance, one-hot vectors
### Word2vec
The first lecture mainly discusses the Word2vec method. It will firstly define the likelihood function with the parameter theta, which is the vector representation of the words, and the hyperparameter m.

After that, it constructs the cost function by taking the negative log-likelihood. For the conditional probability occurring in the cost function, it will be calculated through the softmax function.

After getting the cost function, we can use numerical methods to train the model, that is, to optimize the parameter theta. The lecturer introduces the stochastic gradient descent method, which is a kind of less-cost method than the batch gradient descent method.

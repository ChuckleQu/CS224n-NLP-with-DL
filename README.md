# CS224n-NLP-with-DL
Assignment for CS224n, winter, 2019.
## Lecture 01 - wordvecs1
### How to represent the meaning of a word
For example glasses:
1. denotational semantics: refers to a specific pair of glasses
2. distributional meaning*: "glasses" defined by context
3. localist representation: a representation of a place stored, for instance, one-hot vectors
### Word2vec
The first lecture mainly discusses the Word2vec method. It will firstly define the likelihood function with the parameter theta and the hyperparameter m, where theta is the vector representation of the words.

After that, it constructs the cost function by taking the negative log-likelihood. For the conditional probability occurring in the cost function, it will be calculated through the softmax function.

After getting the cost function, we can use numerical methods to train the model, that is, to optimize the parameter theta. The lecturer introduces the stochastic gradient descent method, which is a kind of less-cost method than the batch gradient descent method.

## Lecture 02 - wordvecs2
### word2vect: Predict the surrounding words using word vectors
1. Skip-grams (SG): Predict context (outside) words given center words
2. Continuous Bag of Words (CBOW): Predict center word from context words
### Negative Sampling
The negative sampling can be added to optimize the skip-gram model. The idea of the negative sampling is to reduce the complexity when doing the optimization (or say, SGD). The general idea of how negative sampling works is that instead of taking the whole corpus to train the model (or to optimize the parameters), we can sample out only a few of the so-called "negative words" to train.

The "negative words" mean the context words that are not in the window of the center word. About how to do the sampling, we use the unigram distribution with a power of 3/4, which results that the less frequent words will be sampled more often.

Actually, I think the expression "the less frequent words will be sampled more often" is not very precise. In fact, the more frequent words will still be sampled with greater probability than the rare ones. However, what this 3/4 power does is trying to reduce the difference of the chosen probability between the frequent words and the rare words, since you can have a view from the graph of y = x ^ (3/4), where it is closer to a uniform distribution (a horizontal line) than y = x.

Intuitively, I think the reason why the creators want to sample rare words more often is that if the words like "the", "a", "an" are sampled too many times, it is some kind of "meaningless" to do the optimization, so we need the rare words as well. Maybe that's why they found out the power of 3/4 is appropriate in their paper.

### Count Based vs. Direct Prediction
1. Count Based: GloVe
2. Direct Prediction: word2vec

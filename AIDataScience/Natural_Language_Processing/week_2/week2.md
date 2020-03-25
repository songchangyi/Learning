# Language modeling and sequence tagging

## Language modeling: it's all about counting!
### Math
- Chain rule : P(w) = P(w1) * P(w2|w1)...P(Wk|w1...w(k-1))
- Markov assumption : P(wi|w1w2...w(i-1)) = P(wi|w(i-n+1)...w(i-1))

### Bigram LM
P(w) = P(w1)P(w2|w1)...P(w(k)|w(k-1))

Problem : normalized separately for each sequence length

P(w) = P(w1|start)P(w2|w1)...P(end|w(k-1))

P(w(i)|w(i-1)) = c(w(i-1)wi) / c(w(i-1))

## Perplexity: is our model surprised with a real text?
### N-gram language model
P(w) = (1:k+1) P(w(i)|w(i-n+1)...w(i-1))

### Log-likelihood maximization

### Extrinsic evaluation

### Intrinsic evaluation
- perplexity
  - the lower the better
  - Use UNK for OOV
  
## Smoothing: what if we see new n-grams?
### Laplacian smoothing
- add-one smoothing : c(w(i)(i-n+1))+1 / c(w(i-1)(i-n+1))+V
- add-k smoothing : c(w(i)(i-n+1))+k / c(w(i-1)(i-n+1))+Vk

### Katz backoff
Try a longer n-gram and back off to shorter if needed

### Interpolation smoothing
lambda1P1 + lambda2P2 + lambda3P3

### Absolute discounting
Compare the counts for bigrams in train and test sets.

### Kneser-Ney smoothing
We need to capture the diversity of contexts of the world.

# Sequence tagging with probabilistic models
## Hidden Markov Models
### Problem
Given a sequence of tokens, infer the most probable sequence of labels for these tokens.

Ex. part of speech tagging, name entity recognition

### Types of named entities
- persons, organizations, locations...
- dates and times, units, amounts...

### Approaches to sequence labeling
1. Rule-based models (EngCG tagger)
2. Separate label classifiers for each token (NB, LR)
3. Sequence models (HMM, MEMM, CRF)
4. NN

### PoS tagging with HMMs
y = argmax P(y|x) = argmax P(x, y)

### Text generation in HMM



# Deep Learning for the same tasks
## Neural Language Models
### Curse of dimensionality
### How to generalize better
- Learn distributed representations for words
- Express probabilities of sequences and learn parameters
### Probabilistic Neural Language Model
- Softmax over components of y
- Feed-forward NN with tons of parameters
- Distributed representation of context words


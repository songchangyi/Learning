# Word and sentence embeddings

## Distributional semantics: bee and honey vs. bee an bumblebee
### Word similarities
- First order co-occurrences : relatedness (bee and honey)
- Second order co-occurrences : similarity (bee and bumblebee)
### Distributional hypothesis
- Pointwise Mutual Information : 
![PMI=log{\frac{p(u,v)}{p(u),p(v)}}=log{\frac{n_{uv}n}{n_u n_v}}](https://render.githubusercontent.com/render/math?math=PMI%3Dlog%7B%5Cfrac%7Bp(u%2Cv)%7D%7Bp(u)%2Cp(v)%7D%7D%3Dlog%7B%5Cfrac%7Bn_%7Buv%7Dn%7D%7Bn_u%20n_v%7D%7D)
- Positive Pointwise Mutual Information :
![pPMI=max(0,PMI)](https://render.githubusercontent.com/render/math?math=pPMI%3Dmax(0%2CPMI))
### Vector Space Models of Semantics
- Input : counts, PMI,...
- Method : SVD,...
- Output : similarity
### What is a context
- C is a vocabulary of contexts
- Usually contexts are words form a sliding window
- W=C and X is a symmetric matrix

## Explicit and implicit matrix factorization
### Singular Value Decomposition (SVD)
X = U (eigenvector in column) * Sigma (square roots of eigenvaleus on the diagonal) * V^T (eigenvector in row)
- keep only first k components
### Weighted squared loss : GloVe
### Word prediction : skip-gram model
- predict context words given a focus word
- model each probability with a softmax
### Skip-gram Negative Sampling (SGNS)
Instead of predicting a word for another word, predict yes or no for word pairs.
- use positive examples from data
- sample negative examples

## Word2vec and doc2vec (and how to evaluate them)
### Word2Vec
Open source and fast
#### Two architectures
- CBOW (Continuous Bag-of-words)
- Continuous Skip-gram (SGNS)
#### Two ways to avoid softmax (too slow)
- negative sampling
- hierarchical softmax
### Evaluation : word similarities
- human judgements
- Spearman's correlation
### Evaluation : word analogies
man:woman is as king:queen
### Doc2Vec
- DM : p(w_i|w_{i-h}...w_{i+h}|d)
- DBOW : p(w_{i-h}...w_{i+h}|d)
### Evaluation : document similarities

## Word analogies without magic: king – man + woman != queen
### BATS dataset
#### Inflectional morphology
#### Derivational morphology
#### Lexicographic semantics
#### Encyclopeidc semantics
### Resume
- word2vec works fine for word similarities but there are many questions with word analogies

## Why words? From character to sentence embeddings
### Morphology can help
Problems:
- Languages with rich morphology
- Low frequency words, OVV words
### FastText
- Represent a word as a bag of character n-grams
- Model a word vector as a sum of sub-word vectors
### Sent2Vec
First ideas :
- Average pre-trained word vectors (word2vec, GloVe, etc)
- Maybe use TF-IDF weights for averaging

Sent2Vec
- Learn sent embedding as a sum of sub-sentence units
### StarSpace
entities and features
#### Mode 3 (sentence embeddings)
Data format : each line is a collection of similar sentences : sent1_word1 sent1_word2...<tab> sent2_word1 sent2_word2
  
### Deep Leaning
- Recurrent Neural Networds (sequence modelling)
- Convolutional Neural Networks (much faster)
- Recursive Neural Networks (hierarchical structure)
### Skip-thought vectors
- Predict next and previous sentences in text
- RNN encoder-decoder architecture

# Topic models
## Topic modeling: a way to navigate through text collections
A soft bi-clustering
### The formal task
- Given : collection of texts as BOW
- Find : probabilities of word in topics & probabilities of topic in documents
### Generative model of texts
Probabilistic Latent Semantic Analysis (PLSA) :
![p(w|d)=\sum p(w|t)p(t|d) ](https://render.githubusercontent.com/render/math?math=p(w%7Cd)%3D%5Csum%20p(w%7Ct)p(t%7Cd)%20)

## How to train PLSA?
### Train
Log-likelihood optimization
### We have just plain texts
![p(t|d,w)=\frac{p(w,t|d)}{p(w|d)}=\frac{p(w|t)p(t|d)}{p(w|d)}](https://render.githubusercontent.com/render/math?math=p(t%7Cd%2Cw)%3D%5Cfrac%7Bp(w%2Ct%7Cd)%7D%7Bp(w%7Cd)%7D%3D%5Cfrac%7Bp(w%7Ct)p(t%7Cd)%7D%7Bp(w%7Cd)%7D)
### Put everything together EM-algorithm

## The zoo of topic models
### Latent Dirichlet Allocation
### Hierarchical topic models
### Dynamic topic models
### Multilingual topic models
### Additive Regularization for Topic Models
### Regularized EM-algorithm
### Visualization
textvis.lnu.se

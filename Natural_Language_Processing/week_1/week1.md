# Introduction to NLP and our course

## Main approaches in NLP
1. Rule-based methods (high precision, low recall)
- regular expressions
- context-free grammars
2. Probabilistic modeling and machine learning
- likelihood maximization
- linear classifiers
3. Deep Learning
- RNN
- CNN

### Deep Learning vs. traditional NLP
- state-of-the-art
- most of research
- look fancy

## Brief overview of the next weeks
- Week 1 : Text classification tasks
- Week 2 : How to predict word sequences
- Week 3 : How to represent a meaning of a word, a sentence or a text
- Week 4 : Sequence to sequence tasks
- Week 5 : Dialogue agents

## Linguistic knowledge
- morphology : different forms of words
- syntax : different relations between words in the sentences
- semantics : meaning
- pragmatics : abstraction

### Libraries
- NLTK
- Stanford parser
- spaCy
- Gensim 
- MALLET

WordNet, BabelNet

# From plain texts to their classification
## Text preprocessing
### What is text
- characters
- words
- phrases and named entities
- sentences
- paragraphs

### What is a word
- split by spaces or punctuation

### Tokenization
- nltk.tokenize.WhitespaceTokenizer
- nltk.tokenize.WordPunctTokenizer
- nltk.tokenize.TreebankWordTokenizer

### Token normalization
Need to try both and choose the best one.
- stemming : 
  - nltk.stem.PorterStemmer
  - caresses->caress 
  - fails on irregular forms, produces non-words
- lemmatization : 
  - nltk.stem.WordNetLemmatizer
  - feet->foot
  - not all forms are reduced

### Further normalization
#### Capital letters
Heuristics : 
- lowercasing the beginning of the sentence
- lowercasing words in titles
- leave mid-sentence words as they are
- ML => hard

#### Acronyms
- regex => hard

## Feature extraction from text

### Bag of words (BOW)

#### Text vectorization
Problems : loose word order, counter are not normalized

#### Preserve some ordering
- N-grams
  - Problem : too many features

#### Remove some n-grams
- high frequency n-grams : stop-words
- low frequency n-grams : typos
- medium frequency n-grams : good

Idea : the n-gram with smaller frequency can be more discriminating because it can capture a specific issue

### TF-IDF
tf * idf

### Better BOW

### Python TF-IDF example
pd.DataFrame(features.todense(), columns=tfidf.get_feature_names())

## Linear models for sentiment analysis
### Sentiment classification
- IMDB, balanced data
- extremely sparse => LR/NB

#### Logistic Regression
- can handle sparse data
- fast to train
- weight can be interpreted

## Hashing trick in spam filtering
- Mapping : may not fit in memory on one machine, hard to synchronize
- easier way is hashing : n-gram => hash(n-gram)%2^20
- sklearn.feature_extraction.text.HashingVectorizer

### Spam filtering is a huge task
personalized features capture "local" user-specific preference

### Vowpal Wabbit
Popular for training linear models.
- uses feature hashing internally
- lots of features
- fast and scales well

# Simple deep learning for text classification
## Neural networks for words
### Neural way (dense)
Word2Vec property : words that have similar context tend to have collinear vectors

You can just average pre-trained word2vec vectors for your text

### A better way : 1D convolutions
Represent 2-grams : convolve the word vectors that are near (in one direction)

### Let's train many filters
- 3,4,5-gram windows with 100 filters each (max pooling)
- MLP on top of these 300 features

## Neural networks for characters
### 1D convolutions on characters
### Max pooling

The deep models work better for large datasets.

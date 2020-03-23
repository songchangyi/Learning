# Data Preparation

## 4.2 Concepts
1. Categorical Encoding
2. Feature Engineering
3. Handling Missing Values

### Options
- SageMaker & Jupyter Notebooks : adhoc
- ETL jobs in AWS Glue : reusable

## 4.3 Categorical Encoding
The process of manipulating categorical variables when ML algorithms expect numerical values as inputs.

categorical variable = categorical feature = discrete feature

- Encoding is necessary for : Linear Regression, CNN
- Encoding is not necessary for : Naive Bayes

### Nominal vs Ordinal

### One-hot Encoding
1. One-hot or not
2. Grouping
3. Mapping Rare Values

### Summary
1. ML algorithm specific
2. No golden rule
3. Text into numbers
4. Many different approaches

## 4.4 Text Feature Engineering
Transforming attributes in our data to make them more useful within our model for the problem at hand.

### Bag-of-words
Tokenizes raw text and creates a statistical representation of the text.

### N-gram
An extension of Bag-of-words which produces groups of words of n size.

Unigram, Bigram, Trigram

### Orthogonal Sparse Bigram (OSB)
Creates groups of words that always include the first word.
- orthogonal : 2 things independent
- sparse : scattered or thinly distributed

### Tf-idf
Consider a document containing 100 words wherein the word cat appears 3 times. 

The term frequency (i.e., tf) for cat is then (3 / 100) = 0.03. 

Now, assume we have 10 million documents and the word cat appears in one thousand of these. 

Then, the inverse document frequency (i.e., idf) is calculated as log(10,000,000 / 1,000) = 4. 

Thus, the Tf-idf weight is the product of these quantities: 0.03 * 4 = 0.12.

### Use Cases
- Spam : N-gram
- Determining subject : Tf-idf, OSB

### Remove punctuation

### Lowercase transformation

### Cartesian product transformation
Combining sets of words together.

### Feature engineering dates

## 4.5 Numeric Feature Engineering
### Feature Scaling
scaling = feature scaling = normalization

- Normalization : x' = (X-minX)/(maxX-minX)

Problem : outliers can throw off. So use Standardization.

- Standardization : z = (X-mean)/std

Summary : 
1. Scaling features
2. Normalization
3. Standardization
4. Translation back

### Binning
Is used to reduce the air of between smail increments of our data.

Quantile binning : equally group values together in bins.

## 4.6 Other Feature Engineering
### Image feature engineering
### Audio
### Dataset formats
- file
  - csv
  - json
  - parquet
  - image
- pipe : 
  - recordIO-protobuf : creates tensor

## 4.7 Handling Missing Values

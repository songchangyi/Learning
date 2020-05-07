# Statistical Machine Translation

## Introduction to Machine Translation
### Parallel data
1. Parallel corpora
  - Europarl
  - Movie subtitles
  - Translated news, books
  - Wikipedia
  - http://opus.lingfil.uu.se/
  
2. Data problems
  - Noisy
  - Specific domain
  - Rare language pairs
  - Not aligned, not enough

### Evaluation
- how to compare two arbitary translations
- low agreement rate between reviewers
- BLEU score - a popular automatic technique = (P_1_gram * ... * P_n_gram)^(1/n)

### The mandatory slide
- Direct
- Syntactic transfer
- Semantic transfer
- Interlingual

## Noisy channel: said in English, received in French
### Noisy Channel
p(f|e)

### Language model : p(e)
p(e)=p(e_1)p(e_2|e_1)...p(e_k|e_1...e_{k-1})

### Translation model : p(f|e)
p(f|e) = p(f1...fJ|e1...eI)

### Word Alignments
One-to-many and many-to-one

Words can disappear or appear from nowhere

## Word Alignment Models
### Word Alignment matrix

### Sketch of learning algorithm
1. Probabilistic model (generative story)
p(f,a|e,theta)
2. Likelihood maximization for the incomplete data
3. EM-algorithm

# Encoder-decoder-attention architecture

## Encoder-decoder architecture
### Sequence to sequence
- Encoder : maps the source sequence to the hidden vector
- Decoder : performs language modeling given this vector
- Prediction : softmax
### Hidden representations are good
But still a bottleneck

## Attention mechanism
- Encoder states are weighted to obtain the representation relevant to the decoder state
- The weights are learnt and should find the most relevant encoder positions

### How to compute attention weights
- Additive attention
- Multiplicative attention
- Dot product also works

### Is the attention similar to what humans do
- For humans : saves time
- For machines : wastes time

### Local attention
1. Find the most relevant position a_j in the source
  - Monotonic alignments
  - Predictive alignments
2. Attend only positions within a window [a_j-h;a_j+h]
  - Compute scores as usual
  - Probably multiply by a Gaussian centered in a_j
  
## How to deal with a vocabulary?
### Outline
- Computing softmax for a large vocabulary is slow
- Even a large vocabulary has OOV words

### Hierarchical softmax
0 to left and 1 to right

How to construct a tree : balanced vs. semantic
- Based on some pre-built ontology
- Based on semantic clustering from data
- Huffman tree
- Random

### Scaling softmax

### Copy mechanism
What do we do with OOV words ? (Scaling softmax is insufficient)
- know the word alignments
- Learn relative positions for UNK tokens with NMT
- Post-process the translation

### Towards open vocabulary
Still problems

### Character-based models

### Hybrid models : the best of two worlds
- work mostly on words level
- go to characters when needed

### Byte-pair encoding

## How to implement a conversational chat-bot?

### Chatbot
Goal-oriented
- narrow domain
- specific questions and tasks
- example : call center
- model : usually retrieval-based

Chit-chat
- general conversation
- human-like experience
- example : entertaining bot
- model ; generative

### Padding
- EOS : end of sentence
- PAD : filler
- GO : start decoding
- UNK : unknown word

### Bucketing
Putting sentences into buckets of different sizes.



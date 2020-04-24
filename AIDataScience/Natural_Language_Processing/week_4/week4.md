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

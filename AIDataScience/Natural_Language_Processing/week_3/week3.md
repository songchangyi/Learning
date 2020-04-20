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

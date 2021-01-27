# 5.1 Natural Language Understanding (NLU)

## 5.1.1 Task-oriented dialog systems

### Intent classification

### Form filling approach to dialog management
- Think of an intent as a form that a user needs to fill in
- Each intent has a set of fields (slots) that must be filled in

Example : nav.directions intent
- @FROM slot : defaults to current geolocaiton
- @TO slot : required

We need a slot tagger to extract slots from utterance.

### Slot filling/tagging
Example : 
- User : Show me the way to HM
- Slot tagger : Show me the way to @TO{HM}

This is token classification task in BIO scheme : 
- Beginning
- Inside
- Outside

Show(O) me(O) the(O) way(O) to(O) History(B-TO) Museum(I-TO)

Train as a sequence tagging task in BIO scheme : a slot is considered to be correct if its range and type are corret

Evaluate intent classifier with accuracy and slot tagger with F1

### Form filling dialog manager (single turn)
User : Give me directions to SF
- Intent classifier : nav.directions
- Slot tagger : @TO{SF}
- Dialog manager : all slots are filled => answer

### How to track context (an easy way)
Both intent classifier and slot tagger need context

Add simple features : 
- Previous intent as a cat feature
- Slots filled in so far with binary feature for each possilbe slot

A better way : memory networks

### How to track a form switch
nav.directions -> nav.find

### Task-oriented dialog system overview
NLU + Dialog manager (state tracking, policy)

## Intent classifier and slot tagger (NLU)

### Intent classifier
- Any model on BOW
- RNN (LSTM, GRU)
- CNN (1D)

### Slot tagger
- Regex
- CRF
- RNN seq2seq
- CNN seq2seq
- Seq2seq with attention

### CNN for sequences : Gated Linear Unit
Gain on score & speed

### ATIS dataset
- Airline Travel Information System
- 4978 utterances
- 17 intents
- 127 slot labels
- SOTA : 1.79% intent err, 95.9 slots F1

### Joint training of intent classifier and slot tagger
95.78+2.02=>95.87+1.57

## Adding context to NLU

## Adding lexicon to NLU

### Add lexicon features to input words
Match every n-gram of input in our lexicon

When multiple overlapping matches:
- prefer exact matches
- prefer longer matches
- prefer earlier matches

### Matches encoding
Use BIOES coding : begin, inside, outside, end, single (single token entity)

### Training details
Augment dataset replacing slot values with values from the same lexicon.

# Dialog Manager

## State tracking in DM

### Dialog Manager
- state tracker (requires hand-crafted states)
  - queries the external db or knowledge base
  - tracks the evolving state of the dialog
  - constructs the state estimation
- policy learner
  - takes the state estimation as input and choose a dialog action
  
### DSTC2 dataset

- Goals
- Method
- Requested slots

### Rule-based state tracking
- train a good NLU
- make simple hand-crafted rules for dialog state change

### Frame tracking

## Policy optimisation in DM

### Dialog policy
Dialog state -> Agent act

### Simple approach : hand crafted rules

### Optimizing dialog policies with ML

#### Supervised Learning

#### Reinforcement Learning
Given only a reward signal

### Joint NLU and DM

## Final remarks

# RASA Core

## Stories
Definition : Rasa stories are a form of training data used to train the Rasa’s dialogue management models.

A specific format : intent <-> action

A training example for the Rasa Core dialogue system is called a story.

### Format
```
## greet + location/price + cuisine + num people    <!-- name of the story - just for debugging -->
* greet
   - action_ask_howcanhelp
* inform{"location": "rome", "price": "cheap"}  <!-- user utterance, in format intent{entities} -->
   - action_on_it
   - action_ask_cuisine
* inform{"cuisine": "spanish"}
   - action_ask_numpeople        <!-- action that the bot should execute -->
* inform{"people": "six"}
   - action_ack_dosearch
```


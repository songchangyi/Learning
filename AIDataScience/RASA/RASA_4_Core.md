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

#### Components
1. Start with a descriptive name : 
```
## story_XXX
```
2. User message : 
```
* inform{"slot_1":val_1, "slot_2":val_2}
```
**Note** : / symbol is a delimiter which can not be used in the intent name
3. Bot action, slot : 
```
  - action_XXX_1
  - slot{"name":"XXX"}
  - action_XXX_2
  - utter_XXX
```
4. End by a newline

#### Actions
Two types of actions: utterance actions and custom actions. 
- utterance actions : hardcoded messages. The responses for utterance actions must begin with the prefix utter_, and must match the name of the response defined in the domain.
- custom actions : custom code being executed. There is no restriction on naming your custom actions (unlike utterance actions), the best practice here is to prefix the name with action_.

#### Events
1. Slot events : 
```
  - slot{"slot_name": "value"}
  - slot{"slot_name": null}
```
2. Form events : 
   - A form action event (e.g. - restaurant_form) is used in the beginning
   - A form activation event (e.g. - form{"name": "restaurant_form"}) is used right after the first form action event
   - A form deactivation event (e.g. - form{"name": null}) is used to deactivate the form



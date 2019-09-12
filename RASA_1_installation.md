# RASA Installation

## Install Virtual Machine

PS : memory >= 2G to avoid the Spacy package installation problem

## Install Anaconda

## Install RASA

#### Create a virtual environment

```
conda create -n rasa python=3.6
```

To remove : 
```
conda remove --name rasa --all
```

### Install RASA

```
sudo apt update
```

```
sudo apt install python3-dev python3-pip
```

```
pip install rasa-x --extra-index-url https://pypi.rasa.com/simple
```

```
conda install spacy
```


```
python -m spacy download en
```

```
rasa init
```

### Common commands

#### Train bot

```
rasa train
```

#### Talk to the trained bot

```
rasa shell
```

#### To get answer with confidence score

```
rasa shell --debug
```

### Files

#### ./data/nlu.md
Training corpus

PS : each time after an update, we need to change domain.yml as well.

#### ./data/stories.md
Dialogs

#### config.yml
Configurations : language, pipeline, etc.


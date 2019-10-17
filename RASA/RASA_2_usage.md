# RASA Usage

Official Tutorial : https://rasa.com/docs/rasa/user-guide/rasa-tutorial/

### Lanch RASA

```
source activate rasa
```

Check RASA version (Linux OS)

```
pip freeze|grep rasa
```

Free disk space taken by anaconda

```
conda clean --all
```

### Create a new project

```
cd WORK_FOLDER_PATH
rasa init
```

### View training data

```
cat data/nlu.md
```

Training data format : https://rasa.com/docs/rasa/nlu/training-data-format/#training-data-format

### Model config

```
cat config.yml
```

Pipeline info : https://rasa.com/docs/rasa/nlu/choosing-a-pipeline/#choosing-a-pipeline


### Write stories
```
cat data/stories.md
```

Story details : https://rasa.com/docs/rasa/core/stories/#stories

### Define domain
```
cat domain.yml
```

### Train model
```
rasa train
```

### Talk to assistant
```
rasa shell
```

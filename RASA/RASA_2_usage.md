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

Json data demo : https://github.com/RasaHQ/rasa/blob/master/data/examples/rasa/demo-rasa.json

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

### Train NLU
```
rasa train nlu
```

### Cross validation
```
rasa test nlu -u data/nlu.md --config config.yml --cross-validation
```

### Comparing NLU Pipelines
```
rasa test nlu --config pretrained_embeddings_spacy.yml supervised_embeddings.yml
  --nlu data/nlu.md --runs 3 --percentages 0 25 50 70 90
```

### Run an NLU server
```
rasa run --enable-api -m models/20191016-110318.tar.gz --endpoints endpoints.yml --port 5002 --credentials credentials.yml
```

- 20191016-110318.tar.gz : model to use
- credentials.yml : 
```
rest:
```
- endpoints.yml : 
```
action_endpoint:
  url: "http://localhost:5055/webhook"
```

Get response : 

- curl
```
curl localhost:5002/model/parse -d '{"text":"hello"}'
```
- python requests
```
import requests

data = '{"text":"hello"}'
url  = 'http://localhost:5002/model/parse'

r = requests.post(url, data=data)
r.json()
```


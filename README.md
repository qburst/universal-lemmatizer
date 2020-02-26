# universal-lemmatizer

A neural sequence-to-sequence model for lemmatization using OpenNMT and pytorch libraries.

The Universal Lemmatizer is part of the **Turku-neural-parser-pipeline** (https://turkunlp.github.io/Turku-neural-parser-pipeline/) with pre-trained models for more than 50 languages, and state-of-the-art lemmatization results in the CoNLL-18 Shared Task on Parsing Universal Dependencies. See TurkuNLP entry at http://universaldependencies.org/conll18/results-lemmas.html.

Needs python3 environment with pytorch installed.

## Running the lemmatizer with pre-trained models

See Turku-neural-parser-pipeline documentation at https://turkunlp.github.io/Turku-neural-parser-pipeline/.

## Training new models  

Inorder to train the model for a new language,  

* Prepare dataset in CONLLU format.  
* This repo contains training and dev data for malayalm in `data` directory.
* Update the `config.yaml` file with configuration for new treebank, Refer example provided in `config.yaml`.
### Training model for malayalam  
Malayalam configuration are provided under  `ml_tdt` key in `config.yaml`  
To start training  
```
python train_lemmatizer.py --treebank ml_tdt  
```
To predict lemmas  
```
python predict_lemmas.py --src /path/to/data/ml-test.conllu --model /path/to/model/model_step_*.pt --output out.txt

```
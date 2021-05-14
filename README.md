# NLP Classification

*Text Classification* or *Text Categorization* (or *Document Classification*) is the process of analyzing natural language texts and labeling them with a predefined set of categories in order to make it easier to manage them.

Typical Use Cases:

* Spam Classification
* Support Ticket Classification
* Sentiment Classification
* Document Labeling

This repository focuses on classification of German texts using state-of-the-art deep learning models.

## Datasets:

* [10k German News Articles](notebooks/10kGNAD/README.md) from Austrian newspaper "DER STANDARD" (9 categories)

## German Language Models

The basis for the text classification are Transformer *Language Models* which were pre-trained on a corpus of German texts. All of following models are available through the [Hugging Face model library](https://huggingface.co/models).

* [bert-base-german-cased](https://huggingface.co/bert-base-german-cased)
* dbmdz/bert-base-german-cased
* dbmdz/bert-base-german-uncased
* dbmdz/distilbert-base-german-europeana-cased
* distilbert-base-german-cased
* deepset/gbert-base
* deepset/gbert-large
* deepset/gelectra-base
* deepset/gelectra-large
* german-nlp-group/electra-base-german-uncased

## Experiments

Many different factors influcence the performance of a NLP model, e.g. from the quality of the training data to the choice of hyperparameters for model tuning. Following we will establish a baseline and then run additional experiements to futher improve the classification accuracy.

### Baseline

Transfer learning with a pre-trained Transformers model, using SimpleTranformers with a default Classification head, on the [10k German News Articles](notebooks/10kGNAD/README.md) dataset.

### Preparation of Training Data

* Text Preprocessing
  * original text - (baseline) no preprocessing
  * lower case - ignore capitalization of words, e.g. at beginning of sentence
  * sentence splitting - one sentence per line (Spacy, [SoMaJo](https://github.com/tsproisl/SoMaJo))
  * removal of special charaters - markup, urls etc.
  * maximum text length - shorter text are harder for learning but longer texts do not necessarily add extra value
* Tokenization
  * word splitting - (baseline) just split words and punctuation
  * German umlauts - keep or use tranliteration
  * compound words - keep or split in parts

### Model Training

* Language Model (LM) Training
  * use pre-trained LM - (baseline) Bert, Distilbert, RoBERTa, Electra, ...
  * language-specific vs. multi-language - the latter ones are larger
* Domain Adaption of Language Model
  * refine LM with task specific data (optional)
* Downstream task training
  * class imbalance - do nothing, oversampling, class weights
  * model head config
    * layers
    * drop out
  * model training
    * batch size
    * learning rate
    * iterations/steps
  * cross validation

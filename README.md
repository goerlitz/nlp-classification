# NLP Classification

*Text Classification* (or *Text Categorization*, *Document Classification*) is the process of analyzing natural language texts and labeling them with a predefined set of categories in order to make it easier to manage them.

Typical use cases are

* Spam Classification
* Support Ticket Classification
* Sentiment Analysis
* Document Labeling

This repository focuses on classification of German texts using state-of-the-art deep learning models.

## Datasets:

* [10k German News Articles](notebooks/10kGNAD/README.md) from Austrian newspaper "DER STANDARD" (9 categories)
* [GermEval18 Sentiments](https://github.com/uds-lsv/GermEval-2018-Data) (coarse and fine)

## German Language Models

The basis for the text classification are Transformer *Language Models* which were pre-trained on a corpus of German texts. All of following German language models are available through the [Hugging Face model hub](https://huggingface.co/models).

**BERT:**
* [bert-base-german-cased](https://huggingface.co/bert-base-german-cased) by Deepset.ai, Jun 2019 - Wiki, OpenLegalData, News (~ 12GB)
* [dbmdz/bert-base-german-cased](https://huggingface.co/dbmdz/bert-base-german-cased) by MDZ Digital Library, Oct 2019 (~ 16GB)
* [dbmdz/bert-base-german-uncased](https://huggingface.co/dbmdz/bert-base-german-uncased) by MDZ Digital Library, Oct 2019 (~ 16GB)
* [dbmdz/bert-base-german-europeana-cased](https://huggingface.co/dbmdz/bert-base-german-europeana-cased) by MDZ Digital Library - Europeana newspapers (~ 51GB)
* [dbmdz/bert-base-german-europeana-uncased](https://huggingface.co/dbmdz/bert-base-german-europeana-uncased) by MDZ Digital Library - Europeana newspapers (~ 51GB)
* **SOTA**: [deepset/gbert-base](https://huggingface.co/deepset/gbert-base) by Deepset.ai + dbmdz, Oct 2020
* [deepset/gbert-large](https://huggingface.co/deepset/gbert-large) by Deepset.ai + dbmdz, Oct 2020

**DistilBERT:**
* [distilbert-base-german-cased](https://huggingface.co/distilbert-base-german-cased)
* [dbmdz/distilbert-base-german-europeana-cased](https://huggingface.co/dbmdz/distilbert-base-german-europeana-cased) by MDZ Digital Library - Europeana newspapers (~ 51GB)

**Electra:**
* [deepset/gelectra-base](https://huggingface.co/deepset/gelectra-base) by Deepset.ai + dbmdz, Oct 2020
* **SOTA**: [deepset/gelectra-large](https://huggingface.co/deepset/gelectra-large) by Deepset.ai + dbmdz, Oct 2020
* [german-nlp-group/electra-base-german-uncased](https://huggingface.co/german-nlp-group/electra-base-german-uncased) by T-Systems + amberoad, Aug 2020

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

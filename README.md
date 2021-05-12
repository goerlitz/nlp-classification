# NLP Classification

*Text Classification* or *Text Categorization* (or *Document Classification*) is the process of analyzing natural language texts and labeling them with a predefined set of categories in order to make it easier to manage them.

Typical Use Cases:

* Spam Classification
* Support Ticket Classification
* Sentiment Classification
* Document Labeling

This repository specifically focuses on Classification of German texts using Deep Learning.

## Datasets:

* [10k German News Articles](notebooks/10kGNAD/README.md) from Austrian newspaper "DER STANDARD"

## Experiments

There are different factors which influence the performance of the text classification. It is necessary to runn different experiments to find a setup which gives the best results.

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

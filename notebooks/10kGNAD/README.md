# Ten Thousand German News Articles from "DER STANDARD"

<div align="center">
  <img src="derstandard.jpg"><br>
</div>

## About

Our goal is to develop a multi-class text classifier for German newspaper articles. We will be using the [Ten Thousand German Newspaper Article Dataset](https://tblock.github.io/10kGNAD/) (10kGNAD). It contains 10,273 German-language news articles, which are categorized into 9 topics.

The source of the news articles is the [One Million Posts Corpus](https://ofai.github.io/million-post-corpus/) which mainly focuses on user comments posted on the Austrian newspaper website [DER STANDARD](http://derstandard.at/). But it also includes the original news arcticles along with some meta data. Fortunately, all articles have been extracted, cleaned and prepared for text classification in the [10kGNAD respository](https://github.com/tblock/10kGNAD) on Github.


## Setup

1. Create Virtual Environment

```console
foo@bar:~$ python3 -m venv venv
foo@bar:~$ source venv/bin/activate
foo@bar:~$ pip install --upgrade -r requirements.txt
```

2. Start Jupyter

```console
foo@bar:~$ jupyter lab
```
3. Run Notebook

## Notebooks Overview

### 1. Explorative Data Analysis

* Basic Data Exploration ([Notebook](10_data_analysis.ipynb))
  * Number and length of articles
  * Names and distribution of categories
* Clustering of Articles (TODO)


### 2. Training a Basic Text Classifier with Transfer Learning

**Goal:** Use a state-of-the-art transfer learning approach to train a baseline classifier.

Use a pre-trained German Language Model from Hugging Face model hub with default model parameters to make it simple. More model tuning can be done later.

#### 2.1. Text Tokenization with pretrained German transformer models

* Compare tokenization of different pretrained German Transformer models ([Notebook](colab/20_transformer_tokenization.ipynb))

#### 2.2. Bert/DistilBert with SimpleTransformers

The SimpleTransformers library makes it easy to implement and train a transformer model in a few lines of code.

* Train a topic classifier with a default SimpleTransformers setup (pretrained German BERT model) ([Notebook](colab/21_default_simpletransformer_classifier.ipynb))

#### 2.3. Bert/DistilBert with Farm

Farm is another library that simplifies training of tranformers models by wrapping setup details of the Tranformers library.

* Train a topic classifier with a default Farm Transformer setup (pretrained German BERT model) ([Notebook](colab/22_default_farm_classifier.ipynb))

#### 2.4. Bert/DistilBert with Tranformers

* Train a topic classifier with a default Hugginface Transformer setup (pretrained German BERT model) ([Notebook](colab/23_default_huggingface_classifier.ipynb))

#### 2.5. Extra: ULMFit with FastAI

* Train classifier on a Pre-trained German FastAI Language Model
* 

### 3. Comparison of Model Performance

**Goal:** Compare the performance of the text classifier (down stream task) when using different pretrained German Language Models and training parameters.

#### 3.1. Compare pretrained Models

BERT vs. DistilBERT vs. Electra

#### 3.2. Compare effects of training parameters

* learning rate
* epochs
* batch size


### 4. Hyperparameter Tuning



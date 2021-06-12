# Ten Thousand German News Articles from "DER STANDARD"

<div align="center">
  <img src="derstandard.jpg"><br>
</div>

## About

**Goal:** Implement a state-of-the-art text classifier using Transfer Learning with pretrained German Transformer Models.

### Dataset
We will be using the [Ten Thousand German Newspaper Article Dataset](https://tblock.github.io/10kGNAD/) (10kGNAD). It contains 10,273 German-language news articles, which are categorized into 9 topics. The source of the news articles is the [One Million Posts Corpus](https://ofai.github.io/million-post-corpus/) which mainly focuses on user comments posted on the Austrian newspaper website [DER STANDARD](http://derstandard.at/). But it also includes the original news arcticles along with some meta data. Fortunately, all articles have been extracted, cleaned and prepared for text classification in the [10kGNAD respository](https://github.com/tblock/10kGNAD) on Github.


### Quick Setup

1. Create Virtual Environment

```console
foo@bar:~$ python3 -m venv venv
foo@bar:~$ source venv/bin/activate
foo@bar:~$ pip install --upgrade -r requirements.txt
```

2. Start Jupyter Lab

```console
foo@bar:~$ jupyter lab
```

## Explorative Data Analysis

All work is done in Jupyter notebooks.

### Basic Data Exploration

Get some descriptive statistics about the news article dataset ([Notebook](10_data_analysis.ipynb)).

* Number and length of articles
* Names and distribution of categories


### Clustering of Articles (TODO)

Using ...

## Transfer Learning with Pretrained German Language Models


### Preliminary: Understanding Tokenization of German Texts

* Compare tokenization of different pretrained German Transformer models ([Notebook](colab/20_transformer_tokenization.ipynb))


### Using SimpleTransformers

SimpleTransformers is an great library which wraps around the excellent HuggingFace Transformer implementation and makes it very easy to train state-of-the-art NLP Models with just a few lines of code. Moreover, it directly integrated with Weights & Biases for evaluation of model performance.

Steps:
1. Train a basic topic classifier based on a pretrained German DistilBert language model using the sensible default settings of SimpleTransformers. ([Notebook](colab/21_default_simpletransformer_classifier.ipynb))
3. Use hyperparameter optimization to improve the model performance.
4. Use advanced hyperparameter optimization to further improve the model performance.


### Comparing Different Pretrained German Transformer Models

* Use different pretrained German Language Models and compare their performance.


### Using Farm

Farm is another library that simplifies training of Transformer models by wrapping setup details of the Hugginface Transformer library.

* Train a topic classifier with a default Farm Transformer setup (pretrained German BERT model) ([Notebook](colab/22_default_farm_classifier.ipynb))


### Using HuggingFace

* Train a topic classifier with a default Hugginface Transformer setup (pretrained German BERT model) ([Notebook](colab/23_default_huggingface_classifier.ipynb))


### Using FastAI (ULMFit)

* Train classifier on a pretrained German FastAI Language Model

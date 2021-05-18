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

### 2. Baseline Classification Model with Transfer Learning

**Goal:** Create a baseline text classifier using a pre-trained German Language Model (from Hugging Face model hub).

* Train classifier on a Pre-trained German BERT Language Model
* Train classifier on a Pre-trained German FastAI Language Model
* Analyse classifier performance

### 3. Comparison of Transformer Models

* Compare tokenization of German texts
* Compare performance of different pretrained Models

### 4. Hyperparameter Tuning



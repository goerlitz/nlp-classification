# 10k German News Articles from "DER STANDARD"

<div align="center">
  <img src="derstandard.jpg"><br>
</div>

## About

Our goal is to develop a multi-class text classifier for German newspaper articles. Therefore we will use the [One Million Posts Corpus](https://ofai.github.io/million-post-corpus/) which contains user comments published on the Austrian newspaper website [DER STANDARD](http://derstandard.at/). While the user posts make up the majority of the data set, we're only interested in the original articles.


When working with the [One Million Posts Corpus](https://ofai.github.io/million-post-corpus/), the first thing we need to do is extract and clean up all newspaper articles. Fortunately, the project [Ten Thousand German Newspaper Article Dataset](https://tblock.github.io/10kGNAD/) (10kGNAD) on [Github](https://github.com/tblock/10kGNAD) is already doing this. It contains 10,273 German-language news articles, which are divided into 9 topics. 


## Quick Start

1. Create Virtual Environment

```console
foo@bar:~$ python3 -m venv venv
foo@bar:~$ source venv/bin/activate
foo@bar:~$ pip install --upgrade -r requirements.txt
```

2. Start Jupyter Notebook

```console
foo@bar:~$ jupyter lab
```

## Notebooks Overview

### 0. Data Preparation

* Fetching the Dataset ([Notebook](00_data_fetching.ipynb))

### 1. Explorative Data Analysis

* General Statistics ([Notebook](10_data_analysis.ipynb))


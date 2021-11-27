# Classification of German Newpaper Articles with Transformer Models

**Goal:** Use different pretrained German Transformer models to create a classifier for the [Ten Thousand German Newspaper Article Dataset](https://tblock.github.io/10kGNAD/).

Note that all implementations need GPU support. Therefore, the notebooks are best run in Google Colab.

# PART I - Intro

## Model Comparison

...

## Tokenizer Comparison

Tokenization is an important preprocessing step with impact on the overall model performance. Hence, different tokenizers are being used by the Transformer models.

* Compare tokenization of different pretrained German Transformer models ([Notebook](colab/10_transformer_tokenization.ipynb))


# PART II - Basic Models

## Model Setup and Training

These examples focus on the basic setup and training of a Transformer-based classification model, with no optimization and using mostly default settings.

* Using SimpleTransformers ([Notebook](colab/20_10kGNAD_simpletransformers_basic.ipynb))
* Using Huggingface Trainer ([Notebook](colab/21_10kGNAD_huggingface_basic.ipynb))
* Using Farm (TODO)

## Performance Comparison of Basic Models


# PART III - Model Optimization

## Hyperparameter Tuning


## Performance Comparison of Optimized Models


# HKUST ELEC4230 Final Group Project: ResAdapter

This repository is a summary of the final group project for HKUST ELEC4230 (Deep Learning for Natural Language Processing), developed by [Chia-Wei Wu](https://github.com/clsied) and [Chia-Hong Hsu](https://scholar.google.com/citations?user=1xEUDBcAAAAJ). The main reference for our project is from [a group project](https://github.com/traviemcg/cs224nfinalproject) of Stanford's NLP class CS224N Winter 2020.

## Dependencies

```
pip install transformers pytorch matplotlib
```

## Overview

This project explores the concept of Transfer Learning for NLP by using adapters to reduce the computational and storage costs of fine-tuning large language models. Instead of fine-tuning the entire model, only the adapter parameters are trained, while the pretrained model parameters remain frozen. We introduce **ResAdapters**, a novel approach that applies residual networks to adapters.

### Our ResNeXt Adapter with BERT

<img src="https://github.com/clsied/2020-ELEC4230-ResAdapter/blob/main/assets/ResNeXt%20Adapter.png" width="350"/>

### An Adapter Cell  
<img src="https://github.com/clsied/2020-ELEC4230-ResAdapter/blob/main/assets/Adapter%20Cell.png" width="200"/>

## Dataset

The test is conducted on the [SQuAD2.0](https://rajpurkar.github.io/SQuAD-explorer/) dataset, with the task of reading and extracting answers from the text for the given question.

## Results

| Model                  | ALL   |       | NoAns |       | HasAns |       |
|------------------------|-------|-------|-------|-------|--------|-------|
|                        | EM    | F1    | EM    | F1    | EM     | F1    |
| **Non Linear**         |       |       |       |       |        |       |
| Adapter               | 30.6  | 31.6  | 54.5  | 54.5  | 4.6    | 6.6   |
| Adapter ResNet        | **43.8**  | **46.1**  | **68.3** | **68.3**  | **17.1**   | **21.8**  |
| **With Attention**     |       |       |       |       |        |       |
| Attention             | 33.2  | 40.0  | **56.8**  | **56.8**  | 7.5    | 21.8  |
| Attention ResNet      | 45.0  | 49.0  | 53.5  | 53.5  | 35.7   | 43.9  |
| Attention ResNeXt     | **42.6**  | **51.4**  | 42.8  | 42.8  | **42.3**   | **60.0**  |


## Full details

Please see the project report [here](https://github.com/clsied/2020-ELEC4230-ResAdapter/blob/main/ResAdapters%20Residual%20Architecture%20in%20Language%20Model%20Adapters.pdf)!

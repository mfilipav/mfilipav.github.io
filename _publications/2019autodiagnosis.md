---
title: "Extreme Multi-Label Classification of Disease Codes From Medical Text"
collection: publications
permalink: /publication/2019autodiagnosis
excerpt: 'Automatic diagnosis code assignment from clinical notes is an important problem since performing it manually is error-prone and requires considerable time and human resources. To solve this multi-label classification problem, we use label representations obtained from the label co-occurence graph to generate embeddings, which are fed into an attentional convolutional network. Although the method does not perform well, potential reasons for sub-optimal results and possible improvements are discussed.'
date: 2019-02-01
venue: 'ETHZ Deep Learning course reports'
paperurl: 'http://mfilipav.github.io/files/2019autodiagnosis.pdf'
citation: 'Filipavicius, Modestas (2019). &quot;Extreme Multi-Label Classification of Disease Codes From Medical Text.&quot; <i>ETHZ reports</i>2005(13285)'
---
![alt text](http://mfilipav.github.io/files/multilabel_clf.png "multilabel clf scheme")

Automatic diagnosis code assignment from clinical notes is an important problem since performing it manually is error-prone and requires considerable time and human resources. To solve this multi-label classification problem, we use label representations obtained from the label co-occurence graph to generate embeddings, which are fed into an attentional convolutional network. Although the method does not perform well, potential reasons for sub-optimal results and possible improvements are discussed.

This project was developed as part of the Deep Learning (Fall 2018) course, lead by Thomas Hofmann, together with Orhun Ozbek, Akmaral Yessenalina, Brynja Sigurpalsdottir

## Idea
The purpose of this project is multi-label classification of disease diagnosis codes (ICD9) in patient discharge notes from MIMIC-III dataset. We compare and improve on the several state-of-the-art deep learning methods (CNNs, Hierarchical Attention Networks, RNNs).

## Models
### Convolutional Attention for Multi-Label classification (CAML) model is described below:
![alt text](http://mfilipav.github.io/files/caml.png "CAML model")


`X` - embedding matrix, with `N` words (truncated to 2,500) and embedding dimension `de`


`H` - non-linear activation matrix, obtained by passing embeddings through a convolutional filter `Wc` with dimensions `d_e` (input embedding), `d_c` (filter output) and `k` (filter width)


`al` - per-label attention

`vl` - vector representation for each label



### Multi-label Classification scheme for medical discharge records is described below:
![alt text](http://mfilipav.github.io/files/multilabel_clf.png "multilabel clf scheme")

1. Learn doctors notes document embeddings with CAML procedure above 
1. Instead of using label vectors as the target variables directly, we obtained 256-dim label graph embeddings by using AttentionWalk algorithm. For each document, corresponding label embeddings are aggregated by taking by averaging. Resulting representation of the document is used as the target vector for multi-target regression.

1. Resulting document embeddings are mapped to the label power set using Multi-Label K-Nearest Neighbor (ML-KNN) algorithm


### Our model resulted in similar metric performance to CAML and CNN state-of-the-art models:

![alt text](http://mfilipav.github.io/files/results.png "results")

## Code
[See our solution in github repo here:](https://github.com/mfilipav/auto-diagnosis)


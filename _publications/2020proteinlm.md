---
title: "Pre-training Protein Language Models with Label-Agnostic Binding Pairs Enhances Performance in Downstream Tasks"
collection: publications
permalink: /publication/2020proteinlm
excerpt: 'Life science practitioners are drowning in unlabeled protein sequences. Natural Language Processing (NLP) community has recently embraced self-supervised learning as a powerful approach to learn representations from unlabeled text, in large part due to the attention-based context-aware Transformer models. In a transfer learning fashion, expensive pre-trained universal embeddings can be rapidly fine-tuned to multiple downstream prediction tasks. 
In this work we present a modification to the RoBERTa model by inputting a mixture of binding and non-binding protein sequences (from STRING database) during pre-training with the Masked Language Modeling (MLM) objective.
Next, we compress protein sequences by 64\% with a Byte Pair Encoding (BPE) vocabulary consisting of 10K tokens, each 3-4 amino acids long.
Finally, to expand the model input space to even larger proteins and multi-protein assemblies, we pre-train Longformer models that support 2,048 tokens.
Our approach produces excellent fine-tuning results for protein-protein binding prediction, TCR-epitope binding prediction, cellular-localization and remote homology classification tasks. We suggest that the Transformer's attention mechanism contributes to protein binding site discovery. Further work in token-level classification for secondary structure prediction is needed. Code available at: https://github.ibm.com/PaccMann/paccmann_proteomics'
date: 2020-10-30
venue: 'NeurIPS'
paperurl: 'https://arxiv.org/abs/2006.33282'
citation: 'Filipavicius, M et al., (2020). &quot;Pre-training Protein Language Models with Label-Agnostic Binding Pairs Enhances Performance in Downstream Tasks.&quot; <i>NeurIPS2020</i>2006(33282)'
---

## A drug discovery framework for antiviral small molecules against SARS-CoV-2:
![alt text](http://mfilipav.github.io/files/proteinLMarch.png "Protein LM architecture")
Proposed architecture is pre-trained by a mixture of binding and non-binding protein sequences, using only the MLM objective. Byte-pair encoding with a 10k token vocabulary enables inputting 64% longer protein sequences compared to character level embedding. `E_i` and `T_i` represent input and contextual embeddings for token `i`. `[CLS]` is a special token for classification-task output, while `[SEP]` separates two non-consecutive sequences.

[Download paper here](http://mfilipav.github.io/files/2020proteinlm.pdf)


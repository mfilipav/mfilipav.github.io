---
title: "PaccMannRL on SARS-CoV-2: Designing antiviral candidates with conditional generative models"
collection: publications
permalink: /publication/2020covid
excerpt: 'With the fast development of COVID-19 into a global pandemic, scientists around the globe are desperately searching for effective antiviral therapeutic agents. Bridging systems biology and drug discovery, we propose a deep learning framework for conditional de novo design of antiviral candidate drugs tailored against given protein targets. First, we train a multimodal ligand--protein binding affinity model on predicting affinities of antiviral compounds to target proteins and couple this model with pharmacological toxicity predictors. Exploiting this multi-objective as a reward function of a conditional molecular generator (consisting of two VAEs), we showcase a framework that navigates the chemical space toward regions with more antiviral molecules. Specifically, we explore a challenging setting of generating ligands against unseen protein targets by performing a leave-one-out-cross-validation on 41 SARS-CoV-2-related target proteins. Using deep RL, it is demonstrated that in 35 out of 41 cases, the generation is biased towards sampling more binding ligands, with an average increase of 83% comparing to an unbiased VAE'
date: 2020-05-27
venue: 'arXiv'
paperurl: 'https://arxiv.org/abs/2005.13285'
citation: 'Born, Jannis et al., (2020). &quot;PaccMannRL on SARS-CoV-2: Designing antiviral candidates with conditional generative models.&quot; <i>arXiv</i>2005(13285)'
---
## A drug discovery framework for antiviral small molecules against SARS-CoV-2:
![alt text](http://mfilipav.github.io/files/paccmann_covid.png "Paccmann RL scheme")
The conditional compound generator, called agent (see **A**), can produce novel structures specifically designed to target a protein of interest. The generative process starts with the encoding of the primary structure of the target protein into a latent space of protein sequences. The representation is fed into a molecular decoder of a separately pretrained molecule VAE to produce a candidate compound. 

Next, the proposed compound is evaluated by a critic (see **B**) composed by: a multimodal deep learning model that predicts protein–drug binding affinity using protein and compound sequences as input, and a QSAR-based score to punish toxicity. By means of the reward given by the critic, a closed-loop system is created and is trained with deep reinforcement learning to maximize a multi-objective reward.


[Download paper here](https://arxiv.org/pdf/2005.13285)


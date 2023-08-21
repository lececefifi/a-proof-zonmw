# Cecilia Kuan - Data Augmentation for Pre-Trained Clinical NLP System
### Master's Degree in "*Linguistics: Text Mining*", VU Amsterdam.

This repository contains the code implemented for the Master's Thesis Project "*Generative Approach of Data Augmentation for Pre-Trained Clinical NLP System*".\
Thesis author: Cecilia Kuan\
Supervisor: Dr. Piek Vossen\

Description
-------------
This is a part of the project [A-PROOF](https://cltl.github.io/a-proof-project), an ongoing collaboration between [AUMC](https://www.amsterdamumc.org/en/about/organization/about-amsterdam-umc.htm) and [CLTL](http://www.cltl.nl/).\

This thesis studies the effect of data augmentation and data sampling on improving the performance of a system classifying patients' functioning using EHRs. 

**Data and Class Labels**
Data sets used in this thesis include 3 real data sets from previous researches, and 1 synthetic data set generated for this thesis. Previous researches use 9 class labels; 9 ICF categories are used for the A-RPOOF porject,

ICF code | Category | Acronym/Label used in repo
---|---|---
b440 | Respiration functions | ADM
b140 | Attention functions | ATT
d840-d859 | Work and employment | BER
b1300 | Energy level | ENR
d550 | Eating | ETN
d450 | Walking | FAC
b455 | Exercise tolerance functions | INS
b530 | Weight maintenance functions | MBW
b152 | Emotional functions | STM

In this thesis, a dual-classifiers approach is used to include the 10th class to represent negative samples, "None".

The real data sets consist of clinical notes from Electronic Health Records (EHRs) in Dutch. Due to privacy constraints, these data cannot be released. Synthetic data set can be found in the `data` folder.

**Experiments and Evaluations**
Experiments are conducted using training sets with different sampling of data, and different fine-tuning model; performance are evaluated using Precision, Recall, and F1 Scores.

**Models**
Model used for synthetic data generation is OpenAI's API with model GPT-3.5. Models used for fine-tuning are [MedRoBERTa.nl](https://huggingface.co/CLTL/MedRoBERTa.nl) and the project's initial system, [A-PROOF ICF-domains Classification](https://huggingface.co/CLTL/icf-domains) created by Jenia Kim.

Repository
----------
The code in this repository are adapted and modified from A-PROOF repository https://github.com/cltl/a-proof-zonmw.


# Project folder structure

```
Cecilia_Kuan_data_generation
└───clf_domains
└───data
└───data_analysis
└───data_generation
└───data_data_process
└───ml_evaluation
└───models
└───nb_data_analysis
└───tools
└───utils
│   .gitignore
│   LICENSE
│   README.md
│   requirements.tx
```

- `/clf_domains`: scripts for training and evaluating a multi-label classification model that detects the 9 ICF domains.
- `/data`: data sets that can be shared
- `/data_analysis`: notebooks to generate statistics for corpus analysis
- `/data_generation`: script and notebook for generating synthetic data
- `/data_process`: scripts for various data processing tasks, incl. processing of raw data, processing annotations, data prep for the machine learning pipeline etc.
- `/ml_evaluation`: notebooks for evaluation of the machine learning models.
- `/models`: model files that can be shared.
- `/tools`: notebooks for processing outputs of dual-classifiers approach
- `/utils`: general helper functions used throughout the repo.

For descriptions of files within each folder, please refer to the READMEs in the individual folders.

## Requirements

The requirements are listed in the [environment.yml](environment.yml) file. It is recommended to create a virtual environment with conda (you need to have Anaconda or Miniconda installed):
```
$ conda env create -f environment.yml
$ conda activate zonmw
```

# Assessing the Impact of OCR Quality on Downstream NLP Tasks 

This repository provides underlying code for the conference paper *'Assessing the Impact of OCR Quality on Downstream NLP Tasks'*

## Citation
TODO

## What is this?
This repository contains code underpinning the conference paper *'Assessing the Impact of OCR Quality on Downstream NLP Tasks'.* This paper assesses the impact of OCR quality on a variety of downstream tasks using a dataset of OCR'd articles from 19th Century newspapers. This repository includes code for downloading and processing the data into a [Pandas](https://pandas.pydata.org/) Dataframe and code for each section of the paper (outlined further below). 

## Setup 
The majority of the analysis is done in Python 3. You can create an environment for running this code using the Anaconda package manager and the environment file includes in this repository. 

### Install the required packages

**Note** While Conda environments are *largely* operating system agnostic we have only tested this environment on macOS. 


1. Install Anaconda following [these instructions](https://docs.anaconda.com/anaconda/install/).

2. Create `ocr_eval` environment:

```bash
conda env create -f environment.yml
```

3. Activate `ocr_eval` environment:

```bash
conda activate ocr_eval
```


## Contents

All of the dependencies for these notebooks should be covered by using the above Conda Environment. 

### 1) [create_trove_dataframe.ipynb](create_trove_dataframe.ipynb)

- This notebook covers the steps required to download Overproof data and process this data into a Pandas Dataframe. 
 

### 2) dictionary_lookup_word_errorrate.ipynb
### 3) aligning_trove.ipynb
### 4) alignment_assessment.ipynb
### 5) linguistic_processing_trove.ipynb


## Acknowledgements

This work is part of the Living with Machines project. Living with Machines is a multidisciplinary programme funded by the Strategic Priority Fund which is led by UK Research and Innovation (UKRI) and delivered by the Arts and Humanities Research Council (AHRC). 

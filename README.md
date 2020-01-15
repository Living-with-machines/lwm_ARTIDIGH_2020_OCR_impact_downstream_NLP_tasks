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

All of the dependencies for these notebooks should be covered by using the above Conda Environment. The notebooks below are presented in the order they appear in the orginal paper.

### 1) [create_trove_dataframe.ipynb](create_trove_dataframe.ipynb)

This notebook
- covers the steps required to download Overproof data and process this data into a Pandas Dataframe. 
- it will take some time to run the first time. The notebook will output the Pandas Dataframe as a [pickle file](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_pickle.html). This will allow for quicker loading of the Dataframe when used in the subsequent notebooks (it will probably be easiest to 'run all cells' and return to the notebook a few hours later)

### 2) [dictionary_lookup_word_errorrate.ipynb](dictionary_lookup_word_errorrate.ipynb) 

This notebook 
- plots dictionary lookup against string similarity between OCR'd and human corrected version of the text
- produces plots comparing Jaccard and Levenstein distance similarity

### 3) aligning_trove.ipynb(aligning_trove.ipynb)

This notebook performs allignement between the two version of the text. Further explanation of the approach taken is outlined in the notebook. 

### 4) alignment_assessment.ipynb(alignment_assessment.ipynb)

This notebook performs an evaluation of the alignments created in the previous notebook. 

### 5) linguistic_processing_trove.ipynb


## Acknowledgements

This work is part of the Living with Machines project. Living with Machines is a multidisciplinary programme funded by the Strategic Priority Fund which is led by UK Research and Innovation (UKRI) and delivered by the Arts and Humanities Research Council (AHRC). 

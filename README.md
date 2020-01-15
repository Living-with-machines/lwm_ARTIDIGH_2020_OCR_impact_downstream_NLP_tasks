# Assessing the Impact of OCR Quality on Downstream NLP Tasks 

This repository provides underlying code for the conference paper *'Assessing the Impact of OCR Quality on Downstream NLP Tasks'*

## Citation
TODO

## What is this?
This repository contains code underpinning the conference paper *'Assessing the Impact of OCR Quality on Downstream NLP Tasks'.* This paper assesses the impact of OCR quality on a variety of downstream tasks using a dataset of OCR'd articles from 19th Century newspapers. This repository includes code for downloading and processing the data into a [Pandas](https://pandas.pydata.org/) Dataframe and code for each section of the paper (outlined further below). 

## Setup 
The majority of the analysis is done in Python 3. You can create an environment for running this code using the Anaconda package manager and the environment file includes in this repository. 

### Install the required packages


**Note** While Conda environments are *largely* operating system agnostic we have only tested this environment on macOS. The [pandarallel](https://github.com/nalepae/pandarallel) Python package which we use for parallelizing some steps in the notebooks only works on windows if executed from the [Windows Subsystem for Linux (WSL)](https://docs.microsoft.com/en-us/windows/wsl/install-win10). If you want to run the notebooks from Windows directly this should be possible by replacing ```parallel_apply``` with ```apply```. This will result in the default Pandas apply function being utilised. This will result in these functions running more slowly. 

---

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

All of the dependencies for these notebooks should be covered by using the above Conda Environment. The notebooks below are presented in the order they appear in the original paper.

### 1) [create_trove_dataframe.ipynb](create_trove_dataframe.ipynb)

This notebook
- covers the steps required to download Overproof data and process this data into a Pandas Dataframe. 
- it will take some time to run the first time. The notebook will output the Pandas Dataframe as a [pickle file](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_pickle.html). This will allow for quicker loading of the Dataframe when used in the subsequent notebooks (it will probably be easiest to 'run all cells' and return to the notebook a few hours later)

### 2) [dictionary_lookup_word_errorrate.ipynb](dictionary_lookup_word_errorrate.ipynb) 

This notebook 
- plots dictionary lookup against string similarity between OCR'd and human corrected version of the text
- produces plots comparing Jaccard and Levenstein distance similarity

### 3) [aligning_trove.ipynb](aligning_trove.ipynb)

This notebook performs alignment between the two versions of the text. Further explanation of the approach taken is outlined in the notebook. 

### 4) [alignment_assessment.ipynb](alignment_assessment.ipynb)

This notebook evaluates the alignments created in the previous notebook. 

### 5) [linguistic_processing_trove.ipynb](linguistic_processing_trove.ipynb)

This notebook assesses the impact of OCR on:

- Part-of-speech tagging accuracy (fine- and coarse-grained)
- Named entity recognition accuracy (matching type, matching type and IOB-tag)
    - Persons: f-score (by quality band)
    - Geopolitical entities: f-score (by quality band)
    - Dates: f-score (by quality band)
- Dependency parsing

### 6) [task_topic_modelling.ipynb](task_topic_modelling.ipynb) 

This notebook goes through the steps of creating topic models using Latent  Dirichlet  Allocation (LDA) using the Gensim implementation. 

### 7) [task_topic_modelling-joint_plots.ipynb](task_topic_modelling-joint_plots.ipynb) 

This notebook performs and evaluation of the topic models created in the above notebook. 

### Language model notebooks 

- These notebooks rely on having a pre-trained LM to fine-tune. This language model will be released alongside a forthcoming paper. This notebook will be updated once this has been released. 

## Acknowledgements

This work is part of the Living with Machines project. Living with Machines is a multidisciplinary programme funded by the Strategic Priority Fund which is led by UK Research and Innovation (UKRI) and delivered by the Arts and Humanities Research Council (AHRC). 

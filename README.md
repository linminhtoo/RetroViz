# RetroViz
Visual Analysis of performance of state-of-the-art models for retrosynthesis
The 3 models are:
- RetroXpert: https://github.com/uta-smile/RetroXpert
- GLN (Graph Logic Network): https://github.com/Hanjun-Dai/GLN
- RetroSim: https://github.com/connorcoley/retrosim
I have retrained all 3 models from scratch on a slightly cleaner version of the USPTO-50K dataset than the original authors. Therefore, the predictions & evaluation statistics I got are slightly different (slightly worse actually, because there is some overlap in train & test reactions, which I removed from the training dataset, making the test set slightly harder). Unfortunately I am unable to release the cleaned data files nor the python scripts yet as it is still a work in progress for another project. See below for the link to the prediction CSV files.

## Data
CSV files containing top-200 proposals from each of the 3 models are uploaded to [this google drive folder](https://drive.google.com/drive/folders/1NX8iZI3xfUzlXkWsfTyFlGj6srlNSQDd?usp=sharing) As the name suggests, ground truth precursors have been filtered out since we don't need them; instead, just a column 'rank_of_true_precursor' is enough to remember the performance of the proposer. This column is 0-indexed (i.e. rank = 0 means the proposer recovered the true reactants). 

## Requirements & Setup instructions
RDKit is the main package to generate the molecular drawings. Pandas is used to manipulate prediction data from CSV files
Tested on Python 3.6
```
    # ensure conda is initialized first
    conda create -n retroviz python=3.6 tqdm pathlib typing scipy pandas joblib -y
    conda activate retroviz

    conda install -y rdkit -c rdkit

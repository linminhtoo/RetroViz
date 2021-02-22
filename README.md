# RetroViz
Visual Analysis of performance of state-of-the-art models for retrosynthesis


## Requirements & Setup instructions
RDKit is the main package to generate the molecular drawings. Pandas is used to manipulate prediction data from CSV files
Tested on Python 3.6
```
    # ensure conda is initialized first
    conda create -n retroviz python=3.6 tqdm pathlib typing scipy pandas joblib -y
    conda activate retroviz

    conda install -y rdkit -c rdkit

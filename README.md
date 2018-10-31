# Bias in Data

# Goal
The goal of this project is to provide a reproducible way to analyze Wikipedia articles data which contains location specific information about wikipedia articles relating to politics and explroing potential bias in Data .

# Data source

This analysis primarily uses two data sources which needs some cleaning for final use. Two data sources are namely:

[2018 World Population Data by Population Research Bureau](https://www.dropbox.com/s/5u7sy1xt7g0oi2c/WPDS_2018_data.csv?dl=0). This datset  provides the population estimates for countries across the world until mid 2018,the data can be accessed from dropbox link provided in the header additionally the data is stored in data folder of this repo as  wiki_population_2018_data.csv .

[Politicians by Country Wikipedia articles](https://figshare.com/articles/Untitled_Item/5513449):. This data contains for each article associated country and unique identifier as rev_id. The data was retrieved using Wikimedia API and stored on Figshare. It is saved for future reference in the data folder of this repo as page_data.csv.

[Ores API](https://www.mediawiki.org/wiki/ORES): This particular api is used offered by ORES which provided a machine learning service to score each article retieved from Wikimedia API to classify them into following categories:
 - FA - Featured article
 - GA - Good article
 - B - B-class article
 - C - C-class article
 - Start - Start-class article
 - Stub - Stub-class article

FA AND GA are considered to be high quality for further reading on quality benchmark from ORES follow this link - [ORES_assesment_criteria](https://en.wikipedia.org/wiki/Wikipedia:Content_assessment#Grades)

# Reproducibility

To ensure reproducibility following set of instruction can be follwed to replicate the results shown in the notebook-hcds-a2_bias_in_data.ipynb
This Code was prepared using Python 3.6 in a Jupyter Notebook environment on Linux system.
 -  Git clone the repo.
 -  Activate a conda environment
 -  Install necessary packages
 -  Run Notebook
```
git clone https://github.com/pshivraj/data-512-a2.git
conda create -n bias_in_data
source activate bias_in_data
pip install pandas json numpy os requests
jupyter notebook 
```

Post this one can use notebook ```hcds-a2_bias_in_data.ipynb``` to follow along with the analysis.

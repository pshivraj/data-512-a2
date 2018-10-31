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

# Data Descriptions

The necessary data required to run the notebook is stored in the ```data``` folder of the repo.

## The  Population Dataset - population estimates for countries across the world until mid 2018.
(data/wiki_population_2018_data.csv)

| Column        | Description
| ------------- |:-------------:|
| Geography     | Name of the location(not always country) |
| Population mid-2018 (millions)      | Population of the geographical locations in millions, as of mid 2018   |

## The Wikipedia Dataset  - articles and its associated country.
(data/page_data.csv)

| Column        | Description
| ------------- |:-------------:|
| page     | Name article |
| country      | Location of political figures    |
| rev_id      | revision id for articles edit/ unique identifier  |

Apart from these two parent data sources the data folder also contains other intermediate data files which were used for the analysis.

 ## Article_quality_with_population- merged data object of wikipedia and population dataset
 (data/article_quality_with_population.csv)
 
 | Column        | Description
| ------------- |:-------------:|
| page     | Name article |
| country      | Location of political figures    |
| rev_id      | revision id for articles edit/ unique identifier  |
| prediction      | article quality prediction using ORES Api |
| population      | Population of the geographical locations in millions, as of mid 2018  |

## Article_per_capita- merged data object of wikipedia and population dataset with per capita calculations.
 (data/article_per_capita.csv)

 | Column        | Description
| ------------- |:-------------:|
| pae     | Name article |
| country      | Location of political figures    |
| rev_id      | revision id for articles edit/ unique identifier  |
| prediction      | article quality prediction using ORES Api |
| population      | Population of the geographical locations in millions, as of mid 2018  |
| article_count      | Number of articles per country    |
| high_quality_article_count      | Number of high quality articles per country   |
| articles_per_population      | articles per capita for a country |
| high_quality_articles_per_population      | high quality articles per capita for a country   |

# Analysis
Merging Wikipedia, population and using ORES API the final data frame is created and stored at (data/article_per_capita.csv) which is used to answer folowing questions:
Analysis of articles. This purpose of this step was to explore the article to check for possible biases in data and also to answer the following questions:
 - 10 highest-ranked countries in terms of number of politician articles as a proportion of country population.
 - 10 lowest-ranked countries in terms of number of politician articles as a proportion of country population.
 - 10 highest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country.
 - 10 lowest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country.

# License
This assignment code is released under the MIT License.

# Writeup




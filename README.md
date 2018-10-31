# Assignment 2 - Bias in Data - DATA 512: Human-Centered Data Science

## Goal of the Project

The goal of this project is to gather and investigate a dataset of Wikipedia articles about politicians from different countries. The data sources are described below.

## Source of Data

1. The data for `Politicians by Country from the English-language Wikipedia` was used from [Figshare](https://figshare.com/articles/Untitled_Item/5513449).
2. The data for countries and their population is taken from [here](https://www.dropbox.com/s/5u7sy1xt7g0oi2c/WPDS_2018_data.csv?dl=0).
3. The data for article quality/rating was retrieved by using the [ORES API](https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model). The data quality from best to worst (as mentioned [here](https://en.wikipedia.org/wiki/Wikipedia:Content_assessment#Grades)) are:
	a.  FA - Featured article
	b.  GA - Good article
	c.  B - B-class article
	d.  C - C-class article
	e.  Start - Start-class article
	f. Stub - Stub-class article

## Data Description
1. **Wikipedia Dataset**

| Column | Meaning |
|------|----|
|page|title of wikipedia page (politician)|
|country|name of the country the politician is from|
|rev_id| revision id|

2. **Population Dataset **

| Column | Meaning |
|------|----|
| Geography | The name of the country or territory |
| Population mid-2018 (millions)| The population of the location as of 2018 (in millions)|

3. **Article Quality Dataset** (created in the [notebook](https://github.com/CoderHam/data-512-a2/blob/master/hcds-a2-bias.ipynb) and stored in [`revid_rating.csv`](https://github.com/CoderHam/data-512-a2/blob/master/revid_rating.csv)

| Column | Meaning |
|------|----|
|article_quality|quality of article as reported by ORES API|
|rev_id|revision id|

4. **Master/Merged Dataset** (on which queries are run for investigation)

| Column | Meaning |
|------|----|
| country | The name of the country|
| article_name | title of wikipedia page (politician)|
| revision_id |revision id|
| article_quality |quality of article as reported by ORES API|
| population |The population of the location as of 2018 (in millions)|

The data is stored in [`master_data.csv`](https://github.com/CoderHam/data-512-a2/blob/master/master_data.csv).

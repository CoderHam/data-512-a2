# Assignment 2 - Bias in Data - DATA 512: Human-Centered Data Science

## Goal of the Project

The goal of this project is to gather and investigate a dataset of Wikipedia articles about politicians from different countries. The data sources and results are described below.

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

## Write-up

What I learned from this exercise:

1. When writing reproducible code, it is important to have exhaustive documentation and simple code that is both easy to read and understand.
2. The study involved using data from external sources to investigate bias in the data and I found this a useful way to validate results for data science and perform simple tests to check for bias.
3. While working with datasets such as this, it is less about programming skills and more about the ability of the individual to critically think about the problem and explain certain trends made visible in the data.

### What did I suspect?

Pages on English Wikipedia about politicians of certain countries about depend on the literacy of the country and how many people from that country tend to speak English.

Since we know that countries with large populations such as India and China do not that the proportionately larger number of politicians, instead of looking at the number of articles per country, scaling it by dividing by population would make sense.

### Results - What I Verified/Found and my Theories about it:

As I thought, countries with small populations such as Tuvalu and Nauru were the ones that had the highest number of articles about politicians as a proportion of the country population and the ones lowest were countries like India, Indonesia and China.

Countries that were not native speakers of English ranked lowest in the $\frac{number\ of\ articles}{total\ population}$ - such as India, Indonesia, China, Uzbekistan and Ethiopia.

## Resources used

These experiments were done using `Python 3.7.1` and run in a `Jupyter Notebook`.
 > Documentation for Python:  [https://docs.python.org/3.7](https://docs.python.org/3.7/)  

> Documentation for Jupyter Notebook:  [https://jupyter-notebook.readthedocs.io/en/latest](https://jupyter-notebook.readthedocs.io/en/latest/)

The following Python packages were used and their documentation can be found at the accompanying links:

1. Pandas - [Documentation](https://pandas.pydata.org/)
2. Numpy - [Documentation](http://www.numpy.org/)
3. Requests - [Documentation](http://docs.python-requests.org/en/master/)

## License

This assignment code is released under the  [MIT License](https://github.com/CoderHam/data-512-a2/blob/master/LICENSE).
The Wikipedia articles are licensed under a variety of CC licenses as shown [here](https://en.wikipedia.org/wiki/Wikipedia:FAQ/Copyright).

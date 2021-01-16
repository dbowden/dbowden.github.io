# Using Python for Academic Research

## Why You Might Want to Use Python

- It is a general purpose programming language. It can be used for data analysis, but also to build websites, apps, and games, and it integrates tightly with the computer's command line, giving it significantly ability to control and automate the functions of the operating system. Perhaps most relevant for research purposes is Python's functionality in the realm of data engineering. Python generally has better tools than dedicated statistics packages for working with unstructured/semistructured data such as raw text, images, audio, video, and website data. It also has sophisticated data pipeline tools that can be used for tasks like passing data between different programs or between a personal computer and a server. If you spend much time working with data that is not already in tabular form, Python will probably make your life easier.
- Dask/big data
- Python is the best tool (or at least tied for best) in categories including machine learning (especially deep learning), spatial analysis, Bayeisan analysis, text analysis, and web scraping.
- Reproducibility
- Use in industry

## Why You Might Not

- Some types of analysis not as well supported as in R, Stata, SPSS, etc.
- Limited citation support

## Useful Packages

- Pandas - basically the Python version of the tidyverse. It teaches Python about dataframes, allows for importing data from a variety of formats including csv, xls, Stata, and JSON. It has lots of tools for data manipulation including aggregation and reshaping wide/long, etc.
- Numpy
- Scipy
- Plotnine
- Stargazer
- Statsmodels
- Linearmodels
- PyLogit
- PySurvival
- Lifelines
- Geopandas
- Pysal
- Causal Inference
  - DoWhy
  - EconML
  - CausalML
  - CausalInference
- Survey data
  - Quantipy
  - samplics
- NetworkX
- PyStan
- pymc3
- mlxtend
- NLTK
- Scikit-Learn - primarily intended for machine learning, but some of the tools for imputing missing data might be useful for inferenatial stats.
- Jupyter
- Pweave
- Anaconda
- countrycode
  

## What is Missing?

- Weighted survey data
- Statistical models and tests for network data. ERGMs aren't terribly hard to build from scratch, but no SAOMs.
- Matching other than basic propensity scores
- Very specialized regression models - ivprobit, ???
- Countrycode conversion
- Frequentist glmer - only Bayesian implementations
- coefplot

## Notes for R Users

- Python is 0-indexed
- It is possible to create multiple objects in one line
- '=' is the only assignment operator
- Some changes to data objects can be done in place. Core Python objects (lists, duples, dictionaries) and objects created by the numpy library (arrays, matrices) are permanently changed any time a modifying operation is called. For example, `example_list.reverse()` will permanently reverse the list. Dataframes created by the pandas library work like R objects - they are only permanently changed if the new version of the object is reassigned to the old name. For example, `example_df.drop_na()` will only print a version of dataframe with NAs removed to the console. To permanently change it, we would need to do: `example_df = example_df.drop_na()`. 
- Periods are operators - sort of a combination of `$` and (`%>%`) - so they shouldn't be used in object or variable names.
- But the standard style guides encourages splitting each step into a separate line
- Many libraries are divided into submodules. Rather than importing every single command from a library as one typically would in R, Python users generally import just a few commands as needed. 

## Differences

```
summary(lm(y ~ x1 + x2, data = sample_data))
```

```
import statsmodels.formula.api as smf

smf.ols('y ~ x1 + x2', data=sample_data).fit().summary()
```
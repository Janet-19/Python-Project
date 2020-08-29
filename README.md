Price Estimation of Used Cars Dataset
==============================

This is final project of Wustl Info 577 Applied Data Science for Practitioners course.

Business Goal and Supporting Objectives of the Project:
------------
In the U.S., the used-car market is more twice the size of the new-car segment and is outpacing it in growth. According to [McKinsey's auto retail micro-market model](https://www.mckinsey.com/industries/automotive-and-assembly/our-insights/used-cars-new-platforms-accelerating-sales-in-a-digitally-disrupted-market), it estimates that Americans buy 39.4 million used cars each year, versus 17.3 million new ones (2018), and that used-vehicle sales will increase faster than new-vehicle sales over the next five years. Compared with buying a relatively expansive new car, selecting a used car becomes a more affordable and popular choice for consumers. 

However, when shopping for a used vehicle, customers always have an overriding concern -- *Am I paying too much?* At the same time, car dealers also have difficulty in car resale price forecasting to ensure the competitiveness and profitability of the used car business. 

Under these considerations, the project aims at establishing a model for used car price prediction considering multiple influencing factors, such as year, condition, color, manafacturer, cylinder, etc. It's will be a good attempt to see: 1) to which degree are used car resale prices predictable; 2) what is the relative accuracy of different prediction methods and are some methods particularly effective. Under price estimation, car owners could know more details about used cars pricing when selling their cars, while car buyers could know whether the resale price is reasonable considering different influencing factors.

Data Source:
------------
The Used Cars Dataset is from [Kaggle](https://www.kaggle.com/austinreese/craigslist-carstrucks-data). and its original source is from [Craigslist](https://geo.craigslist.org/iso/us), the world's largest collection of used vehicles for sales. 

Since the original dataset is too large, I put data sample in [data](https://github.com/Janet-19/Python-Project/tree/master/data) folder instead of uploading the whole dataset.

Environment Requirement
----------------
Detailed environment requirement is shown in [requirement.txt](https://github.com/Janet-19/Python-Project/blob/master/requirements.txt) file.
Use - pip install -r requirements.txt to download the required packages.

Overview of Complete Machine Learning Workflow:
----------------
- Data ingestion: 
> The whole dataset is about 509577 rows with parts of missing values. 

> It has 25 columns, that are id (entry ID), url (listing URL), region (craigslist region), region_url, price (entry price), year (entry year), manufacturer, model, condition, cylinders (number of cylinders), fuel (fuel type), odometer (miles traveled by vehicle), title_status, transmission, vin (vehicle identification number), drive (type of drive), size, type, paint_color, image_url, description, county, state (state of listing), lat (latitude of listing), long (longitude of listing).
- [Exploratory Data Analysis (EDA)](https://github.com/Janet-19/Python-Project/blob/master/notebooks/Exploratory%20Data%20Analysis.ipynb)
> The dataset contains so many columns, here I chose some of the columns I insterested for exploratory data analysis.
- Data Pre-processing
> Considering the heavy worklaod of data pre-processing towards 509577 rows, 25 columns, I divided the whole processes into two parts:

> (1) [Data Pre-processing Part I](https://github.com/Janet-19/Python-Project/blob/master/notebooks/Data%20Pre-processing%20Part%20I.ipynb)
>> In Part I, the data pre-processing task focuses on handling missing, duplicates, uncessary values through using different methods towards numerical and categorical columns.

> (2) [Data Pre-processing Part II](https://github.com/Janet-19/Python-Project/blob/master/notebooks/Data%20Pre-processing%20Part%20II.ipynb)
>> In Part II, the data pre-processing work concerns on categorical encoding (i.e. ordinal encoding, one-hot-encoding) and other feature transformation, as well as data standardization.

- [Data Modelling and Evaluation](https://github.com/Janet-19/Python-Project/blob/master/notebooks/Model%20Training%20%26%20Evaluation%20.ipynb)
> In data modelling, considering it's a regression problem, thus I chose Linear Regression , SGD Regression, Decision Tree Regression, LGBM, XGBOOST algorithms with parameter tuning to train the model respectively. Then, I used Mean Absolute Error, Mean Squared Error, Root Mean Square Error indicators to compare the performance of the above five models.

> After comparison, I found Decision Tree Regression achieves best performance in used car price prediction.

P.S. Since the dataset has so many columns, and each column have different chatacteristics and influencing factors towards car prices. **I chose to implement different handling methods towards different columns separately towards missing values, duplicates, categorical encoding, other feature transformation, as well as data standardization.**

**Compared with other ML workflow towards this dataset in Kaggle, I got improved performance in model training and evaluation after customized feature engineering.**

[Reference & Citations](https://github.com/Janet-19/Python-Project/blob/master/references/reference.md)
------------

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.testrun.org


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>


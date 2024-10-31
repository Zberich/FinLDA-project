# FinLDA Project
## Overview
This project explores Financial Latent Dirichlet Allocation (FinLDA), an advanced topic modeling technique designed to enhance financial market predictions by integrating changes in time series with traditional topic models. FinLDA is built upon the Latent Dirichlet Allocation (LDA) framework, modified specifically to capture the dynamics of financial time series data. Here, we aim to validate the predictive value of FinLDA features in forecasting financial metrics, using machine learning models applied to real-world datasets.

## Background
The integration of textual information, such as news articles, with financial data has shown potential in improving prediction models. Traditional models often overlook the direct influence of financial time series data on extracted textual topics. FinLDA seeks to address this gap by including price change information within the topic generation process, thus producing a set of topic distributions directly informed by market fluctuations. These features, extracted from news and financial data, can then be used as input for various machine learning algorithms.

## Data Sources
### News Articles: Archived news articles from CNN, totaling 37,949 documents covering multiple topics and time periods.
Financial Data: 1-minute interval data for the S&P500 index from January 2019 to December 2022, including price, open, close, low, and high for each record. Data was sourced from Finam.I have made all the data I used available on the repository
### Key Components
### Data Collection and Preparation:

* Cleaned and pre-processed news data by removing stop words, punctuation, and irrelevant characters.
* Tokenized and vectorized using Bag-of-Words and TF-IDF models.
* Calculated 5-minute post-publication price changes in S&P500 data, associating each change with corresponding articles.
* 
## FinLDA Modeling:

* Constructed a modified probabilistic graphical model incorporating price changes into LDA.
* Generated topic distributions that include financial time series information, yielding richer feature sets for financial predictions.
## Machine Learning Prediction:

* Trained Linear Regression and Support Vector Regression (SVR) models using both traditional LDA and FinLDA-generated features.
* Applied Principal Component Analysis (PCA) to reduce dimensionality and retain the most significant FinLDA features.
## Evaluation:

* Compared model performance using metrics such as Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R² score.
* Findings showed FinLDA features yielded more robust performance, especially when combined with PCA for feature reduction.
## Results
* The FinLDA model, when applied with SVR and Linear Regression, demonstrated improved predictive accuracy over standard LDA. The PCA-enhanced FinLDA features led to even stronger results, especially for Linear Regression models. This suggests that FinLDA's approach to integrating time series variations with text data adds substantial value for financial predictions.

## How to Run
* Data Preparation:

* Ensure all text data is preprocessed and tokenized.
* Format financial time series data to align timestamps with associated news articles.
* Run FinLDA:

        * Use the LatentDirichletAllocation module in Gensim to build the FinLDA model.
        * Set parameters for topic numbers and time intervals for price changes.
        * Model Training and Evaluation:
        
        * Train machine learning models using FinLDA features.
        * Apply PCA for dimensionality reduction if needed.
        * Compare performance metrics against baseline LDA-based predictions.

## Conclusion
This project establishes FinLDA as a valuable model for financial prediction, enhancing feature extraction by including time series information in topic generation. Future enhancements could involve fine-tuning the time-lag intervals or exploring domain-specific news sources to further improve predictive accuracy.
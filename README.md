# Identification of Undervalued Football Players in Transfer Markets through NLP-Based News Analysis

## Table of Contents

1. Project Overview
2. Dataset Description
3. Installation and Requirements
4. Methodology
5. Results
6. Usage
7. Limitations and Further Work
8. Contributors

## Project Overview

This project focuses on identifying undervalued football players in the transfer market by using Natural Language Processing (NLP) techniques on football-related news articles. By analyzing how news sentiment, content, and transfer history influence player market values, the system aims to recommend players that clubs can potentially acquire at lower costs.

The system uses Random Forest Regression as the main predictive model and compares it with other models such as Linear Regression, SVR, and XGBoost to find the best fit. The project includes tokenization, sentiment analysis, and feature engineering to extract meaningful insights from textual data and historical market values.

## Key Features:

* Tokenization and Sentiment Analysis of news articles.
* Analysis of player market value trends based on transfer history and news impact.
* Predictive modeling to identify undervalued players.
* Model comparison using MAE, RMSE, and R² score

## Dataset Description

**Note:** The dataset used in this project is proprietary and was provided by a collaborating company. Due to privacy policies, the dataset cannot be distributed publicly. Users interested in replicating or testing the project can substitute their own dataset in a similar format.

1. **Player Details:**
Name, Age, Nationality, Position, Team, Contract Expiry, etc.
2.**Market Value (mkt_val):**
Market Value, Highest Market Value, Date, Last Change.
3. **Transfer History (trans_hist):**
From Club, To Club, Transfer Fee, Market Value, Date.
4.**News Articles (news_feed & miao_feed):**
Title, Content, Author, Date, and Category of football-related news articles.

## Installation and Requirements

### Prerequisites:

* Python 3.x
* Google Colab (for running the project)
* The following libraries need to be installed:
pip install pandas numpy scikit-learn matplotlib seaborn plotly nltk stanza spacy xgboost

## Methodology

1.**Data Preprocessing:**
* Tokenization and cleaning of news articles.
* Feature extraction: combining player details, market value trends, and sentiment analysis 
  from news content.
  
2. **NLP Techniques:**
* Sentiment analysis using Transformer model such as BERT.
* Analysis of news impact on player value using semantic modeling.

3. **Modeling:**
The main model used is Random Forest Regression for predicting player market values.
Model Comparison: Random Forest was compared with Linear Regression, SVR, and XGBoost using metrics like MAE, RMSE, and R² Score.

4. **Evaluation Metrics:**
* Mean Absolute Error (MAE): Measures the average error magnitude.
* Root Mean Squared Error (RMSE): Evaluates the error magnitude in squared units.
* R² Score: Indicates the proportion of variance explained by the model.:

| Model                     | MAE          | RMSE         | R² Score   |
|---------------------------|--------------|--------------|------------|
| **Random Forest**         | 826,014      | 2.89 m       | 0.99       |
| **Linear Regression**     | 2.49 m       | 4.63 m       | 0.98       |
| **SVR**                   | 26.89 m      | 35.16 m      | 0.0004     |
| **XGBoost**               | 881,753      | 3.41 m       | 0.99       |

Here is a visual representation of the errors from model comparison:
![Model Comparison](results/Comparison_of_MAE_for_different_Models.png)


## Key Findings:
***Random Forest Regression** performed the best in predicting player market values with high accuracy, reflected in its low MAE and high R² score.
***Linear Regression** performed decently but was less accurate compared to Random Forest.
***SVR** struggled with the dataset, as shown by its very low R² score.
***XGBoost** was a close competitor to Random Forest, with comparable performance but a slightly higher error.

## Usage

1. **Run the Project** on Google Colab:
* Load your dataset into Colab.
* Execute the notebook to preprocess the data, perform sentiment analysis, and build the models.

2. **View Results:**
* The results are stored in the results/ subfolder, including visualizations like feature importance, model predictions, and error distribution.

3. **Evaluate Predictions:**
* Use the RandomForestRegressor model to predict player values and analyze undervalued transfer targets.

## Limitations and Further Work

### Limitations:
***Data Limitations:** The analysis is constrained by the availability of accurate and up-to-date market value data, and some missing or incomplete player transfer history information.
***Model Generalization:** While Random Forest performed well, additional testing with diverse datasets is needed to ensure the model generalizes across leagues and regions.

## Suggestions for Further Work:
***Expanded Dataset:** Adding more player features (e.g., performance stats, injuries) and a larger variety of news sources could improve model accuracy.
***Time-Series Analysis:** Further research into time-series models could better capture market value fluctuations over time.

## Contributors
* Chinenye Ekene Omejieke - Project Lead
  * Supervisor: Dr. Xia
  * Collaborator: Typewind Ltd
    
Feel free to open issues or contribute to this repository!

## Note:
_This project uses proprietary data provided by the collaborator and thus cannot share the original dataset due to privacy restrictions. If you're interested in replicating the work, please use your own dataset that fits the format described in the documentation._

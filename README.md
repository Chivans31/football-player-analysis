# Identification of Undervalued Football Players in Transfer Markets through NLP-Based News Analysis

## Table of Contents

1. [Project Overview](#project-overview)
2. [Dataset Description](#dataset-description)
3. [Installation and Requirements](#installation-and-requirements)
4. [Methodology](#methodology)
5. [Results](#results)
6. [Usage](#usage)
7. [Future Work](#limitations-and-further-work)
8. [Contributors](#Contributors)


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

2. **Market Value (mkt_val):**
Market Value, Highest Market Value, Date, Last Change.

3. **Transfer History (trans_hist):**
From Club, To Club, Transfer Fee, Market Value, Date.

4. **News Articles (news_feed & miao_feed):**
Title, Content, Author, Date, and Category of football-related news articles.

## Installation and Requirements

### Prerequisites:

* Python 3.x
* Google Colab (for running the project)
* The following libraries need to be installed: pandas, numpy, scikit-learn, matplotlib, nltk, re, torch

## Methodology

1. **Data Preprocessing:**
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
* **Mean Absolute Error (MAE):** Measures the average error magnitude.
* **Root Mean Squared Error (RMSE):** Evaluates the error magnitude in squared units.
* **R² Score:** Indicates the proportion of variance explained by the model.

## Evaluation
### Model Comparison:

| Model                     | MAE          | RMSE         | R² Score   |
|---------------------------|--------------|--------------|------------|
| **Random Forest**         | 826,014      | 2.89 m       | 0.99       |
| **Linear Regression**     | 2.49 m       | 4.63 m       | 0.98       |
| **SVR**                   | 26.89 m      | 35.16 m      | 0.0004     |
| **XGBoost**               | 881,753      | 3.41 m       | 0.99       |


Here is a visual representation of the errors from model comparison:

![Model Comparison](Plots/Comparison%20of%20MAE%20for%20different%20Models.PNG)


##  Results

* **Random Forest Regression** performed the best in predicting player market values with high accuracy, reflected in its low MAE and high R² score.
* **Linear Regression** performed decently but was less accurate compared to Random Forest.
* **SVR** struggled with the dataset, as shown by its very low R² score.
* **XGBoost** was a close competitor to Random Forest, with comparable performance but a slightly higher error.

## Key Findings:

![Comparison_of_Actual_vs_Predicted_Market_Value](Plots/Comparison%20of%20Actual%20vs%20Predicted%20Marke%20Values.PNG)

**Interpretation:** The visual comparison of the actual and predicted market values for a sample of players is represented with the bar plot above.

* **Jude Bellingham:** With the predicted and actual values being approximately 177 million and 150 million respectively, Jude Bellington is considered the most undervalued player.
* **Rodri**, **Victor Osimhen** and **Declan Rice** have predicted values that are visibly higher than their actual values, although not as high as the predicted value of the most undervalued player.
* **Paul Pogba**, **Harry Kane** and **Marion Balotelli** have predicted values (15.1 million, 110.1 million and 1.26 million respectively) which are very close to the actual market values (15 million, 110 million and 1.2 million respectively) which indicates model reliability. 
* **Kelechi Iheanacho** appears to be the least undervalued with a predicted value of 1.64 million and actual value of 1.6 million, demonstrating the model’s ability to generalise well across different players.

## Feature Importance
![Feature Importance](Plots/Feature%20Importance.PNG)

Several key points emerge from these results:

1. **Contract Years Remaining (43%):** With the highest importance, this feature indicates that the number of years left on a player’s contract is a critical factor in determining their market values. Higher market values are seemingly commanded by players with longer contracts and this is likely because they offer more long-term security for potential buyers. There is an alignment between this finding and real-world observations as most clubs often appear to be willing to pay more for players under longer contracts. This is mostly because they want to avoid free transfers or to secure talent for an extended period of time.

2. **Age (42%):** Another dominant factor in market value prediction is the player’s age. Potential for development is often seen to be higher with younger players and this makes them more attractive in the transfer market. The importance of age is emphasised with the fact that its weight is almost as much as that of the contract length, as young players with longer contracts are particularly valuable.

3. **Club Association(2%):** While there are lower importance scores for these club-related features compared to age and contract duration, they still contribute to the model’s predictions. The market value of a player can be impacted by the club he is associated with. Players from higher performance clubs like Real Madrid are often valued more due to brand association, prestige, and media exposure but these are smaller compared to intrinsic player characteristics like age and contract years. 

4. **Sentiment Score (approximately 2%):** Although the importance of sentiment is relatively low, the sentiment score derived from media reports also plays a role. While the media perception and news sentiment surrounding a player can influence market value, features like age and contract length are more significant. However, in specific cases such as sudden spikes in value due to transfer rumours or exceptional media coverage, sentiment could still be considerably relevant. 


## Usage

1. **Run the Project** on Google Colab:
* Load your dataset into Colab.
* Execute the notebook to preprocess the data, perform sentiment analysis, and build the models.

2. **Evaluate Predictions:**
* Use the RandomForestRegressor model to predict player values and analyze undervalued transfer targets.

## Limitations and Further Work

### Limitations:
* **Data Limitations:** The analysis is constrained by the availability of accurate and up-to-date market value data, and some missing or incomplete player transfer history information.
* **Model Generalization:** While Random Forest performed well, additional testing with diverse datasets is needed to ensure the model generalizes across leagues and regions.

## Suggestions for Further Work:
* **Expanded Dataset:** Adding more player features (e.g., performance stats, injuries) and a larger variety of news sources could improve model accuracy.
* **Time-Series Analysis:** Further research into time-series models could better capture market value fluctuations over time.

## Contributors
* Chinenye Ekene Omejieke - Project Lead
  * Supervisor: Dr. Xia
  * Collaborator: Typewind Ltd
    
Feel free to open issues or contribute to this repository!

## Note:
_This project uses proprietary data provided by the collaborator and thus cannot share the original dataset due to privacy restrictions. If you're interested in replicating the work, please use your own dataset that fits the format described in the documentation._

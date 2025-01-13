# US 2024 Presidential Election Prediction

## Project Overview
This project is part of the **Applied Machine Learning (COMS W4995)** course taught by Prof. Vijay Pappu at Columbia University. Our team aimed to tackle the challenging and topical task of predicting the outcome of the 2024 U.S. Presidential Election using machine learning models. By leveraging historical trends, polling data, and advanced feature engineering, we successfully developed and evaluated multiple predictive models.

## Motivation
Forecasting U.S. presidential elections is a complex task influenced by shifting political dynamics and voter behaviors. The polarized nature of the 2024 election required a data-driven approach to analyze historical trends and real-time polling data effectively. This project demonstrates how machine learning can provide insights into such intricate prediction problems.

## Folder Structure
The repository is organized according to the phases of a machine learning pipeline, with each folder being self-sufficient:
- **Data Collection and Cleaning**: Scripts and datasets used for gathering and preprocessing data.
- **Feature Engineering**: Code for creating features like party affiliation, state partisan lean, and more.
- **Model Training**: Implementation of various models including Baseline Bayesian, Linear Regression, Random Forest, Decision Tree, and XGBoost.
- **Evaluation**: Scripts for evaluating model performance using metrics like Mean Absolute Error (MAE) and state-level accuracy.
- **Results**: Outputs from models, including predictions and analysis.

## Datasets
The following datasets were used in this project:
1. **Historical Polling Data (1968–2016)**: Sourced from the MIT Election Lab, featuring over 200,000 records.
2. **Recent Polling Data (2020 & 2024)**: State-level polling averages compiled by FiveThirtyEight.
3. **State-Level Election Results**: Aggregated historical outcomes from public records.

After cleaning and preprocessing, the final dataset contained 136,392 samples.

## Methodology

### **Data Collection and Cleaning**
- Integrated datasets from various sources to create a comprehensive view of electoral patterns.
- Removed duplicates and null values to ensure data consistency across all cycles.

### **Exploratory Data Analysis**
- Check ```EDA.pdf```

### **Feature Engineering**
We engineered features to enhance model performance:
- *Party Affiliation*: Democratic or Republican.
- *Days Until Election*: Temporal proximity of polling data to Election Day.
- *State Partisan Lean*: Classification of states as Republican, Democrat, or Swing based on historical trends.
- *Incumbent Candidate*: Whether the candidate is the incumbent.
- *Incumbent Party*: Whether the party currently holds the presidency.

### **Model Training**
We trained five models on state-level polling data and historical election results:
1. **Baseline Bayesian Model**: Used as a benchmark for comparison.
2. **Linear Regression**: Achieved the best performance with low MAE and high accuracy.
3. **Random Forest**
4. **Decision Tree**
5. **XGBoost**

The training process involved:
- Splitting data into 80% training and 20% testing sets.
- Optimizing hyperparameters using grid search.
- Aggregating predicted vote shares to determine electoral votes.

### **Evaluation Metrics**
Models were evaluated using:
1. **Mean Absolute Error (MAE)**: Measures prediction accuracy for vote shares.
2. **State Accuracy**: Proportion of states where predictions matched actual results.
3. **Prediction Correctness**: Whether the overall winner was correctly predicted.

## Results

| **Model**             | **Harris (DEM)** | **Trump (REP)** | **Winner** | **Correct Prediction** |
|-----------------------|------------------|-----------------|------------|------------------------|
| Baseline (Bayesian)   | 289              | 249             | Harris     | ✗                      |
| Linear Regression     | 247              | 289             | Trump      | ✓                      |
| Random Forest         | 267              | 269             | Trump      | ✓                      |
| Decision Tree         | 267              | 269             | Trump      | ✓                      |
| XGBoost               | 267              | 269             | Trump      | ✓                      |
| Real-Life Result      | 226              | 312             | Trump      | ✓                      |


### Key Insights
- The **Linear Regression model** outperformed others with the lowest MAE and perfect state prediction accuracy.
- Ensemble models like Random Forest and XGBoost also achieved perfect state accuracy but exhibited higher MAE due to potential overfitting.
- The Baseline Bayesian Model struggled significantly in both accuracy and prediction correctness.

## Conclusion
This project demonstrates how machine learning can effectively predict U.S. presidential election outcomes when informed by robust datasets and feature engineering. The Linear Regression model emerged as the most reliable predictor in this case.

## Future Scope
To further improve predictions:
1. Incorporate additional features such as voter demographics or campaign finance data.
2. Explore ensemble methods that combine predictions from multiple models for better generalization.
3. Apply natural language processing (NLP) to analyze sentiment from real-time news or social media data.

## Team Members
Zubair Atha, Eesha Barua, Sibi Marappan, Justin Mathew, Pranitha Natarajen

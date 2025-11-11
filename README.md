# ML-with-Python
This repository contain the 5 core assumptions of Linear regression along with practice notebooks covering a variety of machine learning techniques
- Simple Linear Regression
- Multiple Linear Regression
- Standardization
- Training and Testing
- Dummy Variables
- Cluster Analysis
- Logistic Regression

# Simple Linear Regression - Folder 
The file [Number of Books Read - Simple Linear Regression](/Simple%20Linear%20Regression/Number%20of%20Books%20Read%20-%20SLR.ipynb) goes over the steps to conduct a SLR analysis on a fabricated csv file.

Using a 300-row dataset of BooksRead (target) and HoursSpentReading per week (feature), I fit a **simple linear regression** and walked through standard diagnostics. The OLS fit shows a very strong relationship **(R² = 0.966; F = 8559; p < 1e-200)**. The estimated slope is **≈ 0.25**—each additional hour of weekly reading is associated with about **a quarter of a book more per month**—with an intercept of ≈ 0.24. Assumption checks looked good overall: histograms suggested approximate normality, the scatter hinted at linearity/homoscedasticity, and **Durbin–Watson ≈ 1.87** (near 2) indicated minimal autocorrelation. With an **80/20 train–test split (60 test rows)**, predictions tracked the held-out targets closely (mean **absolute percentage difference ≈ 7.4%**, sd ≈ 8.7%), with the largest errors occurring at very low book counts. Taken together, this single-predictor baseline is **highly explanatory and interpretable**; natural next steps would be to incorporate features like pages/day, session length, or book length and compare against regularized models.

# Weather ML - Folder 
There is a Weather Data csv & Weather Data Regrouped csv inside the Weather ML folder which is used for analysis on: 
- Multiple Linear Regression
- Standardization
- Balancing
- Training and Testing
- Clustering manually and with WCSS

<details>
  <summary>Click to expand</summary>
  
## Weather Data OLS Regression - Notebook
The file [Weather Data OLS Regression](/Weather%20ML/Weather%20Data%20OLS%20Regression.ipynb) goes over:
- Multiple Linear Regression
- Standardization
- Training and Testing
## Weather Data Clustering - Notebook
The file [Weather Data Predictions - Clustering](/Weather%20ML/Weather%20Data%20Predictions%20-%20Clustering.ipynb) goes over:
- Manual K-means clustering with scikit-learn
- Selecting the Number of Clusters with WCSS
- Plotting the Elbow with Standardized Variables
- Analyzing the results
## Weather Data Regrouped Clustering - Notebook
This file [Weather Data Regrouped - Clustering](/Weather%20ML/Weather%20Data%20Regrouped%20-%20Clustering.ipynb) has a new column Weather_Regrouped: a manual grouping/ simplifying of the original weather column and goes over:
- Balancing the dataset
- Standardization
- Manual K-means clustering with scikit-learn
- Selecting the Number of Clusters with WCSS
- Plotting the Elbow with Standardized Variables
- Silhouette Scores
- Analyzing the results

</details>


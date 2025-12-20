# ML-with-Python
This repository contain the 5 core assumptions of Linear regression along with practice notebooks covering a variety of machine learning and statistical techniques.
- Simple Linear Regression
- Multiple Linear Regression
- Standardization
- Training and Testing
- Dummy Variables
- Cluster Analysis
- Logistic Regression

# 2009-CO2-emmissions ML - Folder 
The file [ML OLS Regression with CO2 Data](/2009-CO2-emmissions%20ML/ML%20OLS%20Regression%20with%20CO2%20Data.ipynb) is a regression-powered deep dive into what drives state-level carbon emissions. Includes log-transformed modeling, feature selection, and end-to-end diagnostics for high-accuracy environmental prediction.

**Workflow:**
I used a hybrid workflow where I performed an early train/test split to prevent leakage. On the training set only, I fit an OLS model using statsmodels to perform inference-guided feature selection via Wald tests. After selecting statistically relevant predictors, I refit the final model using scikit-learn and evaluated assumptions and generalization performance on held-out test data.

# Simple Linear Regression - Folder 
[Number of Books Read - Simple Linear Regression](/Simple%20Linear%20Regression/Number%20of%20Books%20Read%20-%20SLR.ipynb) Trains a simple linear regression model to predict how many books are read each month from HoursSpentReading. Utilized assumptions checks, a hold-out test set, and full residual diagnostics on a fabricated csv file.

Using a 300-row dataset containing **BooksRead** (target) and **HoursSpentReading per week** (feature), I fit a **simple linear regression model** and conducted all standard diagnostic checks. The OLS results reveal an exceptionally strong linear association between reading time and books read, with a model fit of **R² = 0.967** and an extremely significant overall relationship (**F-statistic ≈ 7035; p < 1×10⁻¹⁷⁸**).

The estimated slope is **≈ 0.24**, meaning each additional hour spent reading per week corresponds, on average, to **about one-quarter of a book more per month**. 

Model assumptions were evaluated on the **training data (80% split)** and showed strong compliance:
- Histograms suggested **residual normality**.
- The residuals-vs-fitted plot showed **no major nonlinearity or heteroscedasticity patterns**.
- **Durbin–Watson ≈ 2.048** indicated essentially **no autocorrelation**, appropriate for cross-sectional data.

Generalization performance was outstanding. With 60 held-out test observations, the model maintained nearly identical accuracy:
- **R² dropped only slightly from 0.967 → 0.961**,
- **RMSE remained stable (0.212 → 0.213)**,
- **MAE remained nearly identical (0.157 → 0.158)**.

Predictions tracked actual book counts closely, with typical deviations of only a few tenths of a book and the largest errors concentrated among very low book-read values (where proportionate differences are naturally higher). Overall, the model showed **excellent stability and minimal overfitting**, supported by near-identical training and testing errors.

Taken together, this single-predictor model is **highly explanatory, stable, and easy to interpret**. 

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


Problem

Swiggy delivery times vary a lot across restaurants. Some deliver quickly, some slowly, but the reasons are not obvious. The question was: can we predict delivery times and identify what factors really matter?

Approach

I followed the full analytics pipeline, exactly as it would be done in a real-world project:

Data Cleaning

Loaded the dataset, handled encoding issues, and persisted the table into a SQLite database.

Checked for missing and inconsistent values, cleaned numeric and categorical fields.

Validation & Preparation

Verified target (delivery time) integrity.

Standardized features and split data into training and testing sets.

Feature Engineering

Built variables like cuisine count to capture diversity.

Encoded categorical features (city, cuisine).

Scaled numeric features to prepare them for models.

Modeling

Trained Linear Regression, Decision Tree, Random Forest, and XGBoost.

Compared models using RMSE, MAE, and R² on test data.

Applied cross-validation and reduced models using LASSO and feature importances.

Interpretation

Plotted feature importances to understand what drives delivery time.

Explored clustering (K-means) to group restaurants with similar delivery profiles.

Findings

XGBoost performed best with RMSE ≈ 12 minutes, R² ≈ 0.30.

City/location was the strongest predictor, followed by restaurant ratings.

Price and cuisine had smaller effects.

Model reduction (LASSO, Random Forest importances) simplified the model while keeping accuracy almost the same.

Clustering revealed useful restaurant groups (fast and efficient, slow but cheap, balanced premium, etc.).

Predictive signal is there, but limited (~30% variance explained) because key drivers like traffic, time-of-day, or courier supply are missing.

Conclusion

Through this project I went through the complete analytics workflow—from data cleaning and database management on Linux servers, to feature engineering, model training, model reduction, and interpretation. I showed that predicting delivery time is possible to a degree, and the main drivers are structural factors like city and reputation.

This project gave me hands-on experience in data wrangling, modeling, visualization, clustering, and reproducible research, and taught me how to take a messy dataset and turn it into meaningful insights and deployable models.

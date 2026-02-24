# App Rating Prediction using Machine Learning

## Project Overview

This project develops a machine learning regression model to predict app ratings on the Google Play Store using structured app metadata.

App ratings serve as an important indicator of user satisfaction and product quality. The objective of this project is to build a predictive model that estimates ratings based on measurable attributes, enabling data-driven identification of high-potential applications.

This repository demonstrates an end-to-end machine learning workflow including data cleaning, feature engineering, exploratory data analysis, modeling, and evaluation.

---

## Business Objective

Google Play Store promotes promising apps through improved search visibility and recommendation placement.  

The goal of this project is to:

- Predict app ratings using quantitative features  
- Identify key variables influencing app performance  
- Build a baseline regression model  
- Evaluate predictive limitations and suggest improvements  

---

## Dataset

- Source: Google Play Store dataset  
- File Used: `googleplaystore.csv`  
- Target Variable: `Rating`

### Features Used

- Category  
- Reviews  
- Installs  
- Size  
- Price  
- Content Rating  
- Genre  

---

## Data Cleaning and Preprocessing

Significant preprocessing was performed to handle inconsistencies and ensure reliable modeling.

### Data Cleaning

- Removed null values  
- Ensured ratings were within the valid range (1–5)  
- Removed inconsistent records:
  - Reviews greater than installs  
  - Free apps with non-zero price  

### Data Transformation

- Converted `Size` from KB/MB to numeric format  
- Cleaned `Reviews` and `Installs` by removing symbols such as '+' and ','  
- Converted `Price` to float after removing '$'  
- Applied log transformation to Reviews and Installs to reduce skewness  

### Outlier Treatment

- Removed apps priced above $200  
- Removed apps with more than 2 million reviews  
- Removed install values above the 95th percentile  

### Encoding

- Applied one-hot encoding to categorical variables  

---

## Exploratory Data Analysis

Univariate and bivariate analysis was conducted using histograms, boxplots, scatter plots, and correlation analysis.

### Key Insights

- Most apps have ratings between 4.0 and 4.5  
- Reviews and installs show a mild positive relationship with ratings  
- Extremely high-priced apps distort distribution  
- Price and size do not significantly influence ratings  
- Ratings are likely influenced by qualitative factors not captured in the dataset  

---

## Model Development

### Train-Test Split

- 70% Training Data  
- 30% Testing Data  

### Model Used

- Linear Regression (Baseline Model)

---

## Model Performance

| Metric     | Score |
|------------|--------|
| Train R²   | 0.160  |
| Test R²    | 0.113  |

### Interpretation

The model captures limited variance in app ratings. While quantitative variables such as installs and reviews contribute to prediction, app ratings are strongly influenced by qualitative factors such as user experience, performance quality, branding, and user expectations, which are not included in the dataset.

---

## Future Improvements

- Implement ensemble models:
  - Random Forest Regressor  
  - Gradient Boosting  
  - XGBoost  
- Perform hyperparameter tuning  
- Apply cross-validation for robust evaluation  
- Incorporate NLP-based features from:
  - App descriptions  
  - User review sentiment  
- Conduct feature importance analysis  

---

## Technology Stack

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit-learn  

---

## How to Run

```bash
# Clone the repository
git clone <your-repo-link>

# Navigate to the project directory
cd app-rating-prediction

# Install required dependencies
pip install -r requirements.txt

# Run the notebook or script
```

---

## Author

Riya Reddy Mukkari  
B.Tech Computer Science (AI & ML)  
Graduation Year: 2027

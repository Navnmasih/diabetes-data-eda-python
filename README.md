# Diabetes Dataset: Exploratory Data Analysis (Python)

Exploratory data analysis of a public diabetes dataset.

## Dataset
768 records with 8 health indicators (Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age) and a binary Outcome (1 = diabetes).

## What I did
1. Loaded the data and checked its structure, null values and summary statistics
2. Plotted the distribution of Insulin
3. Replaced zero values in the columns with the column mean or median
4. Used box plots to look for outliers
5. Separated input features from the Outcome and standardized the features with StandardScaler
6. Detected outliers with z-scores (threshold 3) and the IQR rule (1.5 x IQR) and compared box plots before and after

## Key findings
- No null values: 768 rows and 9 columns
- Glucose, BloodPressure, SkinThickness, Insulin and BMI all have a minimum of 0, which is not realistic for these measurements. For SkinThickness and Insulin, at least a quarter of the records are 0
- Insulin has a very wide spread (mean about 80, standard deviation about 115, maximum 846)
- About 35% of records have a positive Outcome
- The IQR rule flagged 131 of 768 records (about 17%) as outliers, leaving 637

## Limitations and next steps
- Zero values were replaced using statistics calculated on the original columns, which still include the zeros. A better approach is to treat invalid zeros as missing and fill them with the median of the valid readings, and to leave valid zeros (such as Pregnancies) unchanged
- Next: correlation analysis, a class-balance check, and a simple baseline classification model

## Tools
Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn, Google Colab

## How to run
Open `EDA.ipynb` in Google Colab or Jupyter, place `diabetes.csv` in the same folder, and update the file path in the first cells.

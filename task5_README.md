🧠 Titanic Survival Prediction - Data Analysis Key Findings
This project analyzes the Titanic dataset to explore key factors that influenced passenger survival. The dataset consists of demographic and travel information of passengers from the Titanic disaster.

📂 Datasets
Training Set: 891 entries

Test Set: 418 entries

Data Types: Mix of integer, float, and object types

❗ Missing Values
Age: Missing in both training and test datasets

Cabin: Largely missing in both datasets; dropped

Embarked: Missing values in the training set

Fare: Missing values in the test set

Handling Strategy:

Age and Fare: Filled using median values from training data

Embarked: Filled using mode from training data

Cabin: Dropped from both datasets due to high missing rate

📊 Exploratory Data Analysis (EDA)
🚢 Survival Overview
Majority of passengers did not survive

Pclass 3 had the most passengers

Male passengers outnumbered females

Most passengers embarked from port 'S'

💰 Fare Distribution
Highly right-skewed (most paid low fares)

Survivors tend to have paid higher fares

Pclass 1 associated with higher fares and survival

🔍 Feature Correlation with Survival
Feature	Correlation with Survival
Pclass	-0.34 (negative)
Fare	+0.26 (positive)
Age	-0.08 (weak negative)

🧪 Feature Engineering
🔧 Imputation
Age and Fare: Median

Embarked: Mode

✂️ Feature Dropping
Cabin: Dropped due to extensive missing data

➕ New Features
FamilySize = SibSp + Parch + 1

IsAlone = 1 if FamilySize == 1, else 0

🧒 Age Binning
Binned into 5 groups:

Child

Teenager

Young Adult

Adult

Senior

💸 Fare Binning
Binned using quantile-based method

Fallback mechanism used if distribution is not ideal

Example categories:

Low

Medium

High

Very High (optional, depending on binning method)

🔤 One-Hot Encoding
Applied to categorical features:

Sex

Embarked

AgeBin

FareBin

✅ Summary

The analysis suggests Pclass, Fare, and Sex are the most influential features in survival prediction. Proper handling of missing data and thoughtful feature engineering (like binning and encoding) are essential steps that are done here.

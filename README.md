# Poverty Level Classification Report

## Project Overview
This academic research project aims to develop a **machine learning-based classification system** to accurately identify households across four poverty categories using multi-dimensional socioeconomic indicators from Costa Rican household data.

## Objective
Classify households into four distinct poverty levels:
- **Extreme Poverty** (Level 1)
- **Moderate Poverty** (Level 2)
- **Vulnerable Households** (Level 3)
- **Non-Vulnerable Households** (Level 4)

## Problem Statement
Current government assistance programs rely solely on income-based classification, which fails to capture the multidimensional nature of poverty. This leads to **resource wastage** and **incorrect distribution** of welfare benefits. The project addresses this by incorporating multiple socioeconomic factors including family composition, housing conditions, education, and access to basic amenities.

## Dataset
- **Source**: Costa Rican Household Data (Inter-American Development Bank)
- **Training Data**: 9,557 records with 143 features
- **Test Data**: 23,856 records
- **Class Imbalance**: 62.73% non-vulnerable households (addressed via SMOTE)

### Key Variables
- Family demographics (number, age, gender)
- Housing quality (walls, roof, floor conditions)
- Education level (years of schooling)
- Utilities access (electricity, cooking fuel)
- Economic indicators (rent, assets, disability status)

## Methodology

### Data Preprocessing
1. **Missing Value Handling**: Median imputation for columns with <80% missing data
2. **Categorical Encoding**: Label encoding for household identifiers
3. **Class Imbalance**: SMOTE (Synthetic Minority Over-sampling Technique) applied three times sequentially
4. **Normalization**: Standardized feature scaling

### Feature Selection Approaches
- **AUC-based Variable Importance (VIM)**: Identifies features with strongest predictive power
- **Correlation Analysis**: Selects features with correlation coefficients >0.3 or <-0.3 with target

### Classification Models Evaluated
- Random Forest
- K-Nearest Neighbors (KNN)
- Naive Bayes
- Gradient Boosting

## Key Results

| Model | VIM Feature Set | Correlation Feature Set |
|-------|-----------------|------------------------|
| **Random Forest** | **96.90%** | 91.54% |
| Gradient Boosting | 85.30% | 80.60% |
| KNN Classification | 81.18% | 77.11% |
| Naive Bayes | 67.57% | 65.17% |

**Best Performer**: Random Forest achieved **96.90% accuracy** using the VIM feature set, demonstrating the effectiveness of ensemble methods in poverty classification.

## Key Findings
- **Ensemble methods** (Random Forest, Gradient Boosting) significantly outperform single-model approaches
- **VIM-based feature selection** outperforms correlation-based selection
- **Top predictive features**: Dependency rate, wall/roof conditions, household composition, education level
- Class imbalance handling through SMOTE proved critical for balanced predictions

## Most Important Features
1. Dependency rate
2. Walls in good condition (epared3)
3. Roof in good condition (etecho3)
4. Years of schooling (escolari)
5. Household composition indicators (r4h1, r4m1)
6. Ownership of technology (v18q - tablet)
7. Housing material quality (paredzocalo, paredblolad)

## Technologies & Tools
- **Programming**: Python, R
- **Data Processing**: Pandas, NumPy
- **ML Libraries**: Scikit-learn
- **Visualization**: Matplotlib, Seaborn
- **Feature Engineering**: SMOTE, Random Forest
- **Environment**: Jupyter Notebook

## Significance
This work demonstrates that **multidimensional poverty classification** is more effective than income-alone approaches, providing governments and NGOs with better targeting mechanisms for poverty alleviation programs. The high accuracy achieved enables more equitable resource allocation to households in genuine need.

## Future Work
1. Enhance exploratory data analysis through advanced visualization
2. Fine-tune model hyperparameters for marginal accuracy improvements
3. Develop alternative techniques for class imbalance handling
4. Expand analysis to additional geographic regions and datasets
5. Create interpretable scoring systems for practical policy implementation
